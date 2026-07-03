---
title: "Nonperturbative RG Preview"
description: "A preview of nonperturbative renormalization group methods: what they mean, why they are needed, and how functional, lattice, bootstrap, tensor-network, and Schwinger–Dyson approaches fit together."
sidebar:
  label: "Nonperturbative RG Preview"
  order: 80
level: Advanced
status: "Polished draft"
source: "Wilson and Kogut 1974; Polchinski 1984; Wetterich 1993; Berges, Tetradis, and Wetterich 2002; Delamotte 2012; Rosten 2012; Zinn-Justin 2021; Altland and Simons 2023"
topics:
  - nonperturbative RG
  - functional renormalization group
  - lattice RG
  - Schwinger–Dyson equations
  - tensor networks
  - conformal bootstrap
  - truncation control
canonicalTopics:
  - nonperturbative-renormalization-group
  - functional-rg
  - lattice-rg
  - nonperturbative-qft-methods
researchStatus:
  established:
    - "Wilsonian RG, exact RG identities, lattice coarse graining, Schwinger–Dyson equations, functional RG, tensor-network RG, and bootstrap constraints are standard nonperturbative or semi-nonperturbative tools for studying QFT beyond weak-coupling perturbation theory."
  active:
    - "Systematic error control, gauge-invariant truncations, real-time continuation, fermion sign problems, strongly coupled conformal windows, quantum gravity applications, and the relation between different nonperturbative RG schemes remain active research areas."
---

## Summary

Perturbation theory studies a QFT by expanding around a solvable point, usually a Gaussian fixed point. The renormalization group then improves that expansion by organizing logarithms and scale dependence. That is already powerful, but it is not the whole story. Many important questions are not small-coupling questions:

| Question | Why ordinary perturbation theory struggles |
|---|---|
| Does a theory confine? | The relevant infrared degrees of freedom are not weakly coupled gluons. |
| Is there an interacting fixed point? | The fixed point may sit at strong coupling or in a region with no Lagrangian description. |
| What is the phase diagram? | Competing phases may be separated by non-Gaussian critical behavior. |
| Is a scalar theory trivial in four dimensions? | The question concerns global properties of the continuum limit. |
| What is the mass gap? | A mass gap can be nonanalytic in a weak coupling, such as $e^{-1/g^2}$. |
| What happens in low-dimensional many-body systems? | Collective variables, topology, and strong fluctuations dominate. |

A **nonperturbative RG method** tries to keep the Wilsonian idea — integrate out scale by scale and follow the flow of effective descriptions — without assuming that the answer is a power series in a small coupling.

The main landscape is:

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 56rem;">

![Nonperturbative RG methods map](/figures/renormalization-rg-eft/nonperturbative-rg-methods-map.svg)

<figcaption>

Nonperturbative RG is not one method. It is a family of scale-organized approaches: exact functional identities, functional RG truncations, lattice blocking, tensor-network coarse graining, Schwinger–Dyson hierarchies, and bootstrap constraints. Each keeps different information exact and approximates different information.

</figcaption>
</figure>

This page is a preview. It explains the conceptual map, the core equations, the reliability checks, and the common traps. Full nonperturbative physics belongs in the Nonperturbative QFT volume; here the focus is how RG thinking survives beyond ordinary perturbation theory.

## Prerequisites

You should know [Wilsonian effective actions](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [integrating out modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), [theory space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), [exact RG equations](/renormalization-rg-eft/advanced-rg-methods/exact-rg-equations/), the [Polchinski equation](/renormalization-rg-eft/advanced-rg-methods/polchinski-equation/), and the [Wetterich equation](/renormalization-rg-eft/advanced-rg-methods/wetterich-equation/).

It also helps to know [fixed points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [critical exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [universality](/renormalization-rg-eft/wilsonian-renormalization/universality/), and the difference between a regulator scale, a renormalization scale, and a physical scale from [Conventions and Notation](/renormalization-rg-eft/conventions/).

## Setup and conventions

This page uses Euclidean RG notation unless stated otherwise. The RG scale is denoted by $k$ for functional RG flows and by $t=\log k$ for RG time. A running quantity with subscript $k$ changes as modes are integrated in or out. The ultraviolet input scale is denoted by $\Lambda$, while physical long-distance information is recovered from the $k\to0$ limit.

For functional RG formulas, $R_k$ denotes an infrared regulator and $\Gamma_k^{(2)}$ denotes the second functional derivative of the effective average action with respect to the fields. Traces include momentum, position, internal indices, and a minus sign for fermionic variables when appropriate.

## Core idea

A nonperturbative RG method should do three things.

First, it should introduce a scale parameter $k$ or $\rho$ that separates fluctuations already included from fluctuations still active. The precise parameter depends on the method: an infrared regulator scale in the Wetterich equation, a UV cutoff in a Wilsonian action, a lattice blocking scale, a bond dimension in tensor-network truncations, or a radial cutoff in holographic settings.

Second, it should define scale-dependent data. Examples include

$$
S_k[\phi],
\qquad
\Gamma_k[\phi],
\qquad
\{g_i(k)\},
\qquad
\{C_i(k)\},
\qquad
\text{blocked lattice couplings},
\qquad
\text{effective tensor data}.
$$

Third, it should provide a way to extract universal information:

$$
\text{fixed points},
\qquad
\text{critical exponents},
\qquad
\text{operator dimensions},
\qquad
\text{mass gaps},
\qquad
\text{phase boundaries},
\qquad
\text{universal amplitude ratios}.
$$

The nonperturbative part does not mean “no approximations.” It means that the approximation is not organized only as a small-coupling Feynman expansion.

:::note[The word “nonperturbative”]
“Nonperturbative” is context-dependent. A result can be nonperturbative in the coupling $g$, nonperturbative in the number of fields $N$, nonperturbative in derivatives, nonperturbative in topology, or nonperturbative in lattice spacing. Always ask: nonperturbative with respect to which expansion?
:::

## Functional RG as a running effective action

The most common continuum nonperturbative RG framework is the functional renormalization group. The effective average action $\Gamma_k[\phi]$ is a scale-dependent 1PI effective action in which modes with momenta below $k$ are suppressed by an infrared regulator $R_k$.

With Euclidean conventions, the Wetterich equation is

$$
\partial_t\Gamma_k[\phi]
=\frac12\operatorname{Tr}\left[
\left(\Gamma_k^{(2)}[\phi]+R_k\right)^{-1}\partial_t R_k
\right],
\qquad
 t=\log k.
$$

For fermions and ghosts, the trace includes minus signs. The equation looks one-loop-like, but it is exact because the inverse propagator contains the full field-dependent second functional derivative of $\Gamma_k$.

The limiting behavior is usually arranged so that

$$
\Gamma_{k\to \Lambda}\simeq S_\Lambda,
\qquad
\Gamma_{k\to 0}=\Gamma,
$$

where $S_\Lambda$ is a microscopic or UV action and $\Gamma$ is the full quantum effective action.

The exact equation is too large to solve directly. One projects it onto an ansatz. For a single scalar field, a standard derivative expansion begins with

$$
\Gamma_k[\phi]
=\int d^d x\left[
\frac12 Z_k(\phi)(\partial\phi)^2+U_k(\phi)+O(\partial^4)
\right].
$$

The simplest local-potential approximation sets $Z_k$ constant or equal to one and studies only the running potential $U_k(\phi)$. More refined truncations include field-dependent wavefunction renormalization, higher-derivative operators, multiple fields, gauge constraints, Yukawa terms, composite operators, and symmetry-breaking patterns.

The conceptual gain is that the flow can track nontrivial potentials, phase transitions, and fixed points without expanding the potential around a single minimum at every step.

## Wilsonian exact RG and coarse graining

The Wilsonian version tracks a cutoff-dependent action $S_\Lambda[\phi]$ whose partition function is invariant as the cutoff is varied. In a schematic form,

$$
Z=\int^{|p|<\Lambda}\mathcal D\phi\,e^{-S_\Lambda[\phi]}
$$

should not depend on $\Lambda$ after the action is adjusted correctly. Exact RG equations such as the Polchinski equation implement this idea directly.

A useful schematic form is

$$
\partial_t S_t
=
\frac12\frac{\delta S_t}{\delta\phi}\cdot \dot C_t\cdot\frac{\delta S_t}{\delta\phi}
-\frac12\operatorname{Tr}\left(\dot C_t\frac{\delta^2 S_t}{\delta\phi\delta\phi}\right),
$$

where $C_t$ is a regulated covariance and the dot means contraction over momenta and indices. The first term is classical or tree-like. The second term is fluctuation or loop-like. Together they express invariance of the functional integral under infinitesimal changes of cutoff.

The Wilsonian perspective is excellent for conceptual questions:

| Wilsonian question | Nonperturbative importance |
|---|---|
| What is the continuum limit? | A continuum QFT is a trajectory attracted to a fixed point as $a\to0$. |
| Which couplings require tuning? | Relevant directions determine how many parameters must be adjusted. |
| What is universality? | Many microscopic actions flow to the same infrared fixed point. |
| What is triviality? | The only UV fixed point in a sector may be Gaussian. |
| What is asymptotic safety? | A non-Gaussian UV fixed point may define a continuum theory. |

## Lattice RG and blocking

On a lattice, nonperturbative RG can be made literal. One groups microscopic variables into blocks, integrates or sums over short-distance variables, and obtains a new effective action for coarse variables.

For a spin system, a block transformation may define coarse spins $S_I'$ from microscopic spins $s_i$ by a probability kernel

$$
T(S',s),
\qquad
\sum_{S'}T(S',s)=1.
$$

The blocked action $S'[S']$ is defined by

$$
e^{-S'[S']}=\sum_{s}T(S',s)e^{-S[s]}.
$$

This equation is exact if one keeps all operators generated in $S'$. In practice, one projects onto a finite set of couplings. That projection is the approximation.

For lattice gauge theories, blocking must respect gauge invariance or restore it correctly. The variables are link variables rather than site spins, and Wilson loops become natural observables. Monte Carlo RG, strong-coupling expansions, tensor networks, and gradient-flow-inspired scale setting are all ways of extracting RG information from lattice systems.

Lattice RG is conceptually close to Wilson’s original picture. Its great strength is nonperturbative definition. Its cost is that continuum symmetries, fermions, chiral symmetry, and real-time dynamics can become technically difficult.

## Schwinger–Dyson equations and RG

The Schwinger–Dyson equations are exact identities obtained from invariance of the path integral under field redefinitions. For a scalar field,

$$
0=\int\mathcal D\phi\,\frac{\delta}{\delta\phi(x)}
\left[\mathcal O[\phi]e^{-S[\phi]}\right]
$$

implies

$$
\left\langle
\frac{\delta\mathcal O}{\delta\phi(x)}
-\mathcal O\frac{\delta S}{\delta\phi(x)}
\right\rangle=0.
$$

These equations form an infinite hierarchy relating $n$-point functions to higher-point functions. They are nonperturbative identities, not approximations. They become useful after truncation, closure assumptions, or symmetry input.

RG enters because renormalized Schwinger–Dyson equations must be compatible with scale dependence, anomalous dimensions, and operator mixing. In gauge theories, this compatibility is delicate: truncations must respect Ward identities, Slavnov–Taylor identities, or BRST constraints. A numerically impressive answer that violates gauge identities is often not a controlled answer.

Schwinger–Dyson methods are especially common in studies of chiral symmetry breaking, confinement diagnostics, dynamical mass generation, and strongly coupled gauge theories. They are powerful, but their systematic error bars are often harder to quantify than in lattice Monte Carlo or controlled perturbative expansions.

## Tensor-network RG

Tensor-network RG rewrites a lattice partition function or quantum state as a network of local tensors, then coarse-grains the network by factorization and truncation. Schematically,

$$
Z=\operatorname{tTr}\prod_x T_x
\quad\longrightarrow\quad
Z=\operatorname{tTr}\prod_X T'_X.
$$

Here $\operatorname{tTr}$ denotes contraction of tensor indices across the network. The RG step replaces microscopic tensors $T_x$ by coarse tensors $T'_X$, keeping only the most important singular directions according to a chosen criterion.

This approach is especially natural in low-dimensional statistical systems and quantum many-body systems. It can capture entanglement structure more directly than coupling-space truncations. Fixed points appear as scale-invariant tensors. Relevant perturbations appear as eigenoperators of the linearized tensor RG map.

The main control parameter is often the bond dimension $\chi$. Increasing $\chi$ improves the variational space, but convergence can be subtle near criticality, in fermionic systems, in gauge theories, and in higher dimensions.

## Bootstrap constraints as nonperturbative RG data

The conformal bootstrap is not usually called an RG method, but it supplies nonperturbative information about fixed points. At a conformal fixed point, the theory is encoded by CFT data:

$$
\{\Delta_i,\ell_i,C_{ijk}\}.
$$

Crossing symmetry, unitarity, and the OPE impose constraints on this data. In favorable cases, these constraints isolate islands corresponding to real QFT fixed points, such as the three-dimensional Ising CFT.

From the RG viewpoint, bootstrap data gives the fixed point and its linearized perturbations. Scaling dimensions determine which operators are relevant, marginal, or irrelevant. OPE coefficients determine how deformations collide and generate beta functions in conformal perturbation theory.

Thus the bootstrap is complementary to functional and lattice RG:

| Method | Natural output |
|---|---|
| Functional RG | effective action, beta functions, phase structure |
| Lattice RG | nonperturbative continuum limits and observables |
| Tensor RG | fixed-point tensors and entanglement-aware coarse graining |
| Schwinger–Dyson | correlation-function hierarchies and dynamical self-energies |
| Bootstrap | fixed-point spectra and OPE data |

A robust modern analysis often gains credibility when several of these methods agree.

## What counts as control?

Nonperturbative RG methods can look seductively exact. The equations may be exact, the conceptual diagram may be clean, and the numerical plots may be gorgeous. The danger is that most practical calculations use truncations.

A controlled calculation should answer these questions:

| Check | What it tests |
|---|---|
| Regulator dependence | Do universal outputs stabilize when the cutoff shape changes? |
| Truncation order | Do exponents or masses converge when more operators are included? |
| Symmetry constraints | Are Ward, Slavnov–Taylor, BRST, global symmetry, or anomaly constraints respected? |
| Known limits | Does the method reproduce perturbation theory, large-$N$, exactly solvable models, or lattice benchmarks? |
| Universal versus nonuniversal data | Are scheme-dependent couplings being mistaken for physical predictions? |
| Continuum extrapolation | Is the lattice spacing or UV cutoff being removed consistently? |
| Finite-size effects | Are results stable as volume or bond dimension increases? |

The central discipline is: **exact equation plus uncontrolled truncation is not an exact result**.

## Example: scalar criticality without small coupling

Consider the three-dimensional Ising universality class. Perturbation theory near four dimensions uses the $\epsilon$ expansion. Direct three-dimensional perturbation theory requires resummation. Lattice simulations are nonperturbative. Functional RG provides another continuum route.

A derivative expansion ansatz for a $\mathbb Z_2$-symmetric scalar theory is

$$
\Gamma_k[\phi]
=\int d^3x\left[
\frac12 Z_k(\phi)(\partial\phi)^2+U_k(\phi)+\cdots\right],
\qquad
U_k(\phi)=U_k(-\phi).
$$

After defining dimensionless variables, fixed points solve flow equations of the schematic form

$$
\partial_t u(\varphi)= -d u + \frac{d-2+\eta}{2}\varphi u' + \text{threshold functions depending on }u''.
$$

The Wilson–Fisher fixed point is a nontrivial solution $u_*(\varphi)$. Linearizing around it gives eigenvalues related to critical exponents:

$$
\delta u(t,\varphi)=\sum_n c_n e^{-\theta_n t}v_n(\varphi).
$$

The most relevant even perturbation gives $\nu=1/\theta_t$. The leading odd perturbation gives the magnetic exponent data. The anomalous dimension $\eta$ appears once wavefunction renormalization is included.

This calculation is not exact in a finite derivative expansion, but it is genuinely nonperturbative in the quartic coupling. Its credibility comes from convergence checks and comparison with lattice, bootstrap, high-temperature expansions, and resummed perturbation theory.

## Example: a mass gap from dimensional transmutation

In an asymptotically free theory, the running coupling satisfies schematically

$$
\mu\frac{dg}{d\mu}=-b_0g^3+O(g^5),
\qquad b_0>0.
$$

The RG-invariant scale is

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]\left[1+O(g^2)\right].
$$

A mass gap of order $\Lambda$ is invisible in a power series in $g^2$ around $g=0$. Any method that hopes to derive the gap must access information nonanalytic in $g$. Lattice gauge theory, semiclassical methods in special compactifications, large-$N$ methods, Schwinger–Dyson truncations, and functional RG can all contribute, but in different regimes and with different kinds of control.

This is a perfect example of why “RG-improved perturbation theory” and “nonperturbative RG” are not the same thing. The first improves a weak-coupling expansion. The second tries to follow the theory when no weak-coupling expansion controls the answer.

## Gauge theories: the hard case

Gauge theories make nonperturbative RG harder. The difficulty is not only strong coupling; it is redundancy. A regulator or truncation can break gauge symmetry, and the result must either preserve the symmetry exactly or restore it through modified identities.

The choices include:

| Strategy | Advantage | Cost |
|---|---|---|
| Lattice gauge theory | exact gauge invariance with link variables | Euclidean, expensive, fermion and continuum subtleties |
| Background-field FRG | background gauge covariance | split-symmetry identities and truncation issues |
| Gauge-fixed FRG | standard continuum fields | modified Slavnov–Taylor identities must be controlled |
| Gauge-invariant variables | physical observables only | often nonlocal and technically hard |
| Schwinger–Dyson in gauges | direct propagator and vertex studies | gauge dependence and vertex truncation control |

For gauge theories, universal quantities should not depend on gauge choice, regulator shape, or field parametrization. Demonstrating that independence is part of the calculation, not a decorative afterthought.

## Boundaries

This page does not try to teach full lattice gauge theory, tensor-network algorithms, numerical conformal bootstrap, Schwinger–Dyson phenomenology, resurgence, or confinement. Those belong in dedicated volumes and chapters. The purpose here is to locate these methods in the RG map.

It also does not claim that every method called “nonperturbative RG” has the same reliability. Some settings have extremely precise control; others are exploratory. The responsible question is always: **what is exact, what is truncated, what is tested, and what is universal?**

## Common pitfalls

**Thinking nonperturbative means exact.** Nonperturbative calculations often use approximations. The word describes what the approximation is not, not what it automatically proves.

**Confusing a functional equation with its truncation.** The Wetterich equation and Polchinski equation are exact identities. A finite ansatz for $\Gamma_k$ or $S_k$ is not exact.

**Forgetting redundant directions.** RG flow in coupling space includes field-redefinition directions. Universal exponents live in the quotient by redundancies.

**Overinterpreting regulator-dependent data.** Fixed-point coordinates, threshold functions, and intermediate running couplings can depend on scheme. Critical exponents and scaling dimensions should not.

**Ignoring symmetry identities.** In gauge theories and theories with anomalies, symmetry constraints are not optional. A truncation that violates them can produce physically meaningless fixed points.

**Treating agreement as proof.** Agreement between two uncontrolled truncations is encouraging. It is not the same as a controlled continuum limit or rigorous bound.

## Relations to other pages

This page synthesizes ideas from [Exact RG Equations](/renormalization-rg-eft/advanced-rg-methods/exact-rg-equations/), [Polchinski Equation](/renormalization-rg-eft/advanced-rg-methods/polchinski-equation/), [Wetterich Equation](/renormalization-rg-eft/advanced-rg-methods/wetterich-equation/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/).

It points outward to Nonperturbative QFT for confinement, mass gaps, lattice field theory, instantons, solitons, and resurgence; to CFT and Bootstrap for fixed-point data; to Computational QFT for algorithms and benchmarking; and to Gauge Theories and the Standard Model for physical gauge dynamics.

## Research status

The basic Wilsonian and functional RG frameworks are established. Their exact equations are formal identities once regulators and definitions are specified. What remains active is the art of making them predictive in hard theories: gauge theories, real-time systems, finite density, gravity, chiral fermions, topological phases, and strongly coupled conformal sectors.

Especially active questions include:

- how to preserve or restore gauge symmetry in functional truncations;
- how to quantify systematic errors in derivative and vertex expansions;
- how to combine FRG with lattice data, bootstrap data, and Schwinger–Dyson constraints;
- how to use nonperturbative RG in quantum gravity and asymptotic safety;
- how to extend real-time and nonequilibrium RG methods with controlled analytic continuation.

## Exercises

### Exercise 1: Exact equation versus truncation

Explain why the Wetterich equation can be exact while a calculation using

$$
\Gamma_k[\phi]=\int d^d x\left[\frac12 Z_k(\partial\phi)^2+U_k(\phi)\right]
$$

is not exact.

<details><summary><strong>Solution</strong></summary>

The Wetterich equation is an identity for the full scale-dependent effective average action $\Gamma_k$. The exact $\Gamma_k$ generally contains all operators allowed by the symmetries: arbitrary powers of fields, arbitrary derivative terms, nonlocal structures in special limits, and composite operator dependence.

The displayed ansatz keeps only a potential and a standard kinetic term with constant $Z_k$. It drops higher derivatives such as $(\partial\phi)^4$, field-dependent wavefunction factors $Z_k(\phi)$, and infinitely many other allowed structures. Substituting the ansatz into the exact equation and projecting back onto the ansatz defines an approximation.

</details>

### Exercise 2: Relevant directions and tuning

Suppose a fixed point has two relevant directions and all other directions are irrelevant. How many microscopic parameters must generically be tuned to reach the critical surface flowing into that fixed point?

<details><summary><strong>Solution</strong></summary>

Generically, one must tune two parameters. Relevant directions grow under flow away from the fixed point. To land on the critical surface attracted to the fixed point in the infrared, the components along all relevant directions must be adjusted to zero or to the desired critical values. Irrelevant components die away automatically.

This is the Wilsonian reason that relevant operators are associated with sensitivity to microscopic data.

</details>

### Exercise 3: Nonanalytic mass scale

Show that the scale

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]
$$

has no Taylor expansion in nonnegative powers of $g^2$ around $g=0$.

<details><summary><strong>Solution</strong></summary>

Let $x=g^2$. The function is $e^{-1/(2b_0x)}$. For $x>0$ it is nonzero, but as $x\to0^+$ it goes to zero faster than any power of $x$:

$$
\lim_{x\to0^+}\frac{e^{-1/(2b_0x)}}{x^n}=0
$$

for every positive integer $n$. All derivatives at $x=0$ vanish if one extends the function by zero at the origin. Its Taylor series around zero is therefore identically zero, but the function is not zero for $x>0$. Hence the dependence is nonanalytic and cannot be recovered from an ordinary perturbative power series.

</details>

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–200.
- J. Polchinski, “Renormalization and Effective Lagrangians,” *Nuclear Physics B* **231** (1984) 269–295.
- C. Wetterich, “Exact Evolution Equation for the Effective Potential,” *Physics Letters B* **301** (1993) 90–94.
- J. Berges, N. Tetradis, and C. Wetterich, “Non-Perturbative Renormalization Flow in Quantum Field Theory and Statistical Physics,” *Physics Reports* **363** (2002) 223–386.
- B. Delamotte, “An Introduction to the Nonperturbative Renormalization Group,” in *Renormalization Group and Effective Field Theory Approaches to Many-Body Systems* (2012).
- O. J. Rosten, “Fundamentals of the Exact Renormalization Group,” *Physics Reports* **511** (2012) 177–272.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, third edition, especially the renormalization group and nonequilibrium chapters.

## Version history

- 2026-06-19: First polished draft. Added conceptual map, method comparison, functional and Wilsonian RG orientation, control criteria, examples, exercises, and references.
