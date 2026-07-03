---
title: "Universality Classes"
description: "Explains universality classes as basins of attraction of RG fixed points and distinguishes universal data from microscopic details."
sidebar:
  label: "Universality Classes"
  order: 6
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Cardy 1996; Goldenfeld 1992; Pelissetto and Vicari 2002; Altland and Simons 2023."
topics:
  - universality classes
  - basins of attraction
  - order parameters
  - critical phenomena
  - scaling data
  - RG fixed points
canonicalTopics:
  - universality-classes
  - rg-basins-of-attraction
  - critical-phenomena
  - fixed-point-data
researchStatus:
  established:
    - "Universality classes are standard RG equivalence classes: many microscopic systems can share the same long-distance fixed point and therefore the same universal critical data."
  active:
    - "Identifying universality classes remains active for constrained systems, deconfined criticality, disorder, long-range interactions, gauge-matter systems, nonequilibrium dynamics, and systems with generalized symmetries or anomalies."
---

## Summary

A **universality class** is a family of systems whose long-distance critical behavior is controlled by the same RG fixed point. The microscopic Hamiltonians, lattice structures, atoms, molecules, and short-distance cutoff schemes can be completely different; after coarse graining, their flows enter the same basin of attraction.

The practical slogan is

$$
\text{same fixed point}
\quad\Longrightarrow\quad
\text{same universal critical data}.
$$

The universal data include critical exponents, scaling functions, amplitude ratios, operator dimensions, and, at a conformal fixed point, OPE coefficients after conventional normalizations. Nonuniversal data include the critical temperature, microscopic lattice spacing, normalization of fields, and most amplitudes.

For example, a three-dimensional uniaxial magnet, a lattice Ising model, and a liquid-vapor transition can all flow to the same Ising universality class. The statement is not that these systems are microscopically similar. They are not. The statement is that after the irrelevant details have died away, the long-distance singular physics is the same.

:::note[One sentence to remember]
A universality class is not a list of models that look alike microscopically; it is a basin of attraction in theory space, labeled by a fixed point and its relevant perturbations.
:::

## Prerequisites

You should know [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/), and [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/).

It helps to have at least one concrete statistical system in mind, such as the Ising model or an $O(N)$ spin model. The conceptual definition is RG-theoretic, but examples prevent the phrase “basin of attraction” from floating off into pure weather-report metaphysics.

## Core idea

Universality is the reason critical phenomena are simple enough to be a science. A real magnet contains atoms, crystal anisotropies, defects, phonons, dipolar forces, and microscopic exchange interactions. A fluid contains molecules, nonuniversal equation-of-state data, and short-distance chemistry. Yet near a continuous critical point, both can display the same exponents and scaling functions.

The Wilsonian explanation is that coarse graining removes irrelevant microscopic details. In theory space, a microscopic system is a point with infinitely many coordinates:

$$
S=\sum_i g_i\int d^d x\,\mathcal O_i(x).
$$

A renormalization step changes the coordinates $g_i$. A critical point is controlled by a fixed point $g_*$. Near that fixed point, only finitely many directions are relevant for an ordinary critical point. All irrelevant perturbations shrink under the RG, so many different microscopic theories collapse onto the same long-distance scaling behavior.

This is why universality classes are more precise than similarity classes. The Ising universality class is not “systems that look like the Ising model.” It is the long-distance fixed point reached by systems with one real scalar order parameter, short-range interactions, the right dimensionality, and no extra relevant perturbations left untuned.

## Setup and conventions

This page uses Euclidean statistical-field-theory language. The number $d$ denotes the dimension of the classical statistical system or Euclidean field theory. The same ideas apply to relativistic quantum critical points after the usual Euclidean continuation. For nonrelativistic quantum critical points with dynamical exponent $z\ne1$, the effective scaling is anisotropic and the universality class also includes dynamic information.

The basic variables are:

| Symbol | Meaning |
|---|---|
| $S$ | Euclidean action or dimensionless effective Hamiltonian |
| $g_i$ | couplings in theory space |
| $g_*$ | fixed-point couplings |
| $u_i$ | scaling fields near the fixed point |
| $y_i$ | RG eigenvalues of scaling fields in the IR convention |
| $\mathcal O_i$ | local operators at or near the fixed point |
| $\xi$ | correlation length |

The IR convention used in this chapter is that $b>1$ is a coarse-graining factor. A scaling field transforms as

$$
u_i' = b^{y_i}u_i.
$$

A perturbation is relevant if $y_i>0$, irrelevant if $y_i<0$, and marginal at linear order if $y_i=0$.

A universality class is defined after specifying which observables and which scaling regime are being discussed. Static critical exponents, boundary exponents, dynamic exponents, and finite-size scaling functions can involve related but distinct universality data.

## Definition in RG language

Let $\mathcal T$ be theory space: the space of all local actions compatible with broad assumptions such as dimension, locality, field content, and symmetries. An RG transformation $R_b$ maps an action to a coarse-grained action:

$$
S\longmapsto R_b S.
$$

A fixed point satisfies

$$
R_bS_*=S_*
$$

up to field normalizations and redundant coordinate changes. The **basin of attraction** of $S_*$ is the set of actions that flow toward $S_*$ after relevant perturbations are tuned to the critical surface.

More precisely, an ordinary critical point has a critical surface $\mathcal C_*$ consisting of actions whose RG trajectories approach $S_*$ in the infrared:

$$
S\in\mathcal C_*
\quad\Longrightarrow\quad
R_bS\to S_*
\quad\text{as}\quad b\to\infty.
$$

The codimension of $\mathcal C_*$ is the number of relevant perturbations that must be tuned. For the ordinary Ising critical point, one usually tunes temperature and sets the magnetic field to zero. If the field is allowed, the magnetic perturbation is also relevant.

Two microscopic systems are in the same universality class when their critical trajectories approach the same fixed point and their physical observables can be matched to the same fixed-point operators. The second clause matters: the same fixed point can have many operators, and a microscopic observable may project onto several of them. The leading singular behavior is controlled by the most relevant allowed projection.

## What data are universal?

A universality class is not merely a set of critical exponents. Critical exponents are the most visible universal data, but the fixed point contains more information.

| Data | Universal? | Comment |
|---|---|---|
| Critical exponents | yes | determined by RG eigenvalues and operator dimensions |
| Scaling dimensions | yes | dimensions of operators at the fixed point |
| OPE coefficients | yes after normalization | part of conformal data when the fixed point is a CFT |
| Scaling functions | yes up to metric factors | depend on normalization conventions for scaling fields |
| Amplitude ratios | often yes | individual amplitudes are usually nonuniversal |
| Critical temperature $T_c$ | no | depends on microscopic details |
| Lattice spacing $a$ | no | part of the UV definition |
| Bare couplings | no | coordinates in microscopic theory space |
| Field normalization | no | can be changed by rescaling fields |

A common example is the correlation length:

$$
\xi_\pm=\xi_{0,\pm}|\tau|^{-\nu}.
$$

The exponent $\nu$ is universal. The amplitudes $\xi_{0,+}$ and $\xi_{0,-}$ are not, but their ratio $\xi_{0,+}/\xi_{0,-}$ can be universal within a class.

Similarly, a two-point function at criticality has the form

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=\frac{C_\mathcal O}{|x|^{2\Delta_\mathcal O}}.
$$

The exponent $\Delta_\mathcal O$ is universal. The coefficient $C_\mathcal O$ depends on the normalization of $\mathcal O$. Once operators are normalized by a convention, OPE coefficients and higher-point data become universal fixed-point data.

## What labels a universality class?

There is no one-line label that works in every problem. Still, several pieces of information are usually decisive.

### Dimension

The dimension $d$ is one of the strongest labels. The Ising model in two dimensions, three dimensions, and four dimensions does not have the same interacting critical theory.

The upper critical dimension is also important. For the short-range Ising and $O(N)$ models, the upper critical dimension is

$$
d_c=4.
$$

For $d>4$, the Gaussian fixed point controls the leading critical exponents, although dangerous irrelevant variables affect some scaling laws. For $d<4$, the interacting Wilson–Fisher fixed point controls the ordinary short-range transition.

### Symmetry and order parameter

The symmetry of the order parameter is often the first practical label. The standard $O(N)$ universality classes have an $N$-component real order parameter

$$
\boldsymbol\phi=(\phi^1,\ldots,\phi^N)
$$

with approximate $O(N)$ symmetry. The cases

$$
N=1,
\quad N=2,
\quad N=3
$$

correspond roughly to Ising, XY, and Heisenberg order parameters.

But symmetry alone is not enough. One must also know which perturbations are allowed. A cubic anisotropy can be irrelevant for some $N$ and relevant for others. If it is relevant, it changes the universality class unless it is tuned away or forbidden by symmetry.

### Range of interactions

Short-range interactions and long-range interactions can lead to different fixed points. A power-law interaction can introduce a nonlocal quadratic term. Schematically,

$$
S_2\sim \int\frac{d^dp}{(2\pi)^d}\,
\phi(p)\left(p^\sigma+r\right)\phi(-p),
$$

rather than the short-range $p^2+r$ form. If the nonlocal term is sufficiently important at small momentum, the universality class changes.

Thus “same symmetry” does not guarantee “same universality class.” Locality and the low-momentum kinetic structure matter.

### Relevant perturbations

A universality class includes a statement about what has been tuned. The tricritical Ising point and the ordinary Ising critical point both involve a scalar order parameter and $\mathbb Z_2$ symmetry, but they are different fixed points. The tricritical point requires an additional tuning because another relevant perturbation is present.

In Landau language, an ordinary Ising critical point can be represented by

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4+\frac{v}{6!}\phi^6+\cdots,
\qquad u>0.
$$

A tricritical point occurs when the quartic coupling is tuned through zero and the sextic term stabilizes the potential:

$$
r=0,
\qquad u=0,
\qquad v>0.
$$

The extra tuning means a different fixed point and a different universality class.

### Conservation laws and dynamics

The static universality class does not determine the dynamic universality class. Dynamics depends on conservation laws, reversible terms, noise, and whether the order parameter is conserved.

For example, an Ising-like order parameter with purely relaxational nonconserved dynamics belongs to a different dynamic universality class from a conserved scalar density, even though the static exponents may be the same. In this volume we focus mostly on static and Euclidean critical behavior. Dynamic universality belongs more naturally with finite-temperature, hydrodynamic, and nonequilibrium QFT.

### Boundaries, defects, and geometry

A bulk universality class does not uniquely determine boundary critical behavior. Boundary conditions define additional RG problems. The ordinary, extraordinary, and special surface transitions of Ising-like systems are different boundary universality classes associated with the same bulk critical theory.

Similarly, defects, interfaces, impurities, and finite-size geometry can carry their own universal data. A boundary condition can be irrelevant in the bulk but relevant for a boundary observable. The boundary is not a decorative edge; it is a lower-dimensional QFT coupled to the bulk.

## Standard examples

The table below is intentionally schematic. Its purpose is orientation, not a replacement for precision exponent tables.

| Universality class | Typical systems | Fixed-point description |
|---|---|---|
| Mean-field | systems above upper critical dimension; sufficiently long-range models | Gaussian fixed point with dangerous irrelevant variables |
| Ising | uniaxial magnets, liquid-vapor critical points, binary mixtures | $\mathbb Z_2$ scalar Wilson–Fisher fixed point |
| XY | superfluid helium transition, planar magnets, superconducting phase variables in some regimes | $O(2)$ Wilson–Fisher fixed point or BKT physics in two dimensions |
| Heisenberg | isotropic magnets | $O(3)$ Wilson–Fisher fixed point in three dimensions |
| $O(N)$ | $N$-component order parameters | $O(N)$ Wilson–Fisher family |
| Tricritical Ising | endpoints where first-order and second-order lines meet | tricritical scalar fixed point with extra relevant tuning |
| Percolation | connectivity transitions in random media | $q\to1$ Potts-type fixed point |
| Self-avoiding walk | long polymers in good solvent | $N\to0$ limit of $O(N)$ model |
| BKT | two-dimensional XY systems, thin superfluids, vortex unbinding | line of fixed points and vortex fugacity flow |

The entries hide many caveats. Real materials have anisotropies, disorder, dipolar forces, finite-size effects, crossover scales, and experimental limitations. The universality claim is about the asymptotic scaling regime, not every measurement at every scale.

## Landau–Ginzburg viewpoint

The Landau–Ginzburg–Wilson construction gives a practical route from microscopic systems to candidate universality classes. Choose an order parameter $\phi$, write the most general local action consistent with symmetries, and study its RG flow.

For a $\mathbb Z_2$-odd scalar order parameter, the Euclidean action begins

$$
S=\int d^d x\left[
\frac12(\partial\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4+\frac{v}{6!}\phi^6+\cdots
\right].
$$

The $\mathbb Z_2$ symmetry forbids odd powers of $\phi$. Near the ordinary critical point, $r$ is relevant and must be tuned. The quartic coupling flows to the fixed-point value. Higher powers and derivative interactions are usually irrelevant near the Wilson–Fisher fixed point, so they do not change leading critical exponents.

For an $O(N)$ vector order parameter, the action begins

$$
S=\int d^d x\left[
\frac12\partial_\mu\phi^a\partial^\mu\phi^a
+\frac12 r\phi^a\phi^a
+\frac{u}{4!}(\phi^a\phi^a)^2+
\cdots
\right].
$$

The symmetry and dimensionality select the candidate fixed point. The RG then decides whether additional allowed perturbations are relevant or irrelevant.

This logic is powerful, but not magic. It can miss topological terms, gauge constraints, dangerously irrelevant variables, long-range tails, disorder, nonlocal degrees of freedom, and deconfined variables that are not obvious in a naive order-parameter field.

## Beyond the simplest Landau picture

The cleanest universality classes are those of ordinary symmetry-breaking critical points. Modern QFT contains many broader examples.

### Gauge constraints

Some systems have emergent gauge fields or constraints. The critical theory may not be expressible solely in terms of the naive order parameter. Deconfined critical points are the famous warning label here: the natural critical variables can be fractionalized fields coupled to gauge fields, while the Landau order parameters appear as composite operators.

Whether a proposed deconfined critical point is continuous, weakly first order, or controlled by a nearby complex fixed point can be subtle. The word “universality class” is still meaningful, but the data needed to identify it are richer than a symmetry-breaking pattern.

### Disorder

Quenched disorder can be relevant or irrelevant. The Harris criterion gives a useful first diagnostic: for uncorrelated weak disorder coupled to the local transition temperature, disorder is perturbatively irrelevant if

$$
\nu d>2.
$$

If disorder is relevant, the flow may reach a new random fixed point. If disorder is strong, rare regions, infinite-randomness fixed points, and Griffiths effects can appear. Then the universality class may include activated rather than power-law scaling.

### Topology and anomalies

Some quantum critical systems are constrained by anomalies, symmetry-protected topological response, or higher-form symmetries. These structures can forbid a trivially gapped symmetric phase and restrict the possible IR fixed points. In such cases, universality class labels may include global symmetry realization, anomaly data, and allowed line or surface operators, not only local order parameters.

### Long-range forces

Coulomb interactions, dipolar interactions, and power-law couplings can change scaling. Sometimes a long-range interaction is screened or irrelevant; sometimes it changes the fixed point. One must inspect the scaling dimension of the long-range perturbation at the putative short-range fixed point rather than assuming it disappears.

### Marginal directions and lines of fixed points

A universality class can be a point, but it can also involve a line or manifold of fixed points. Two-dimensional compact boson CFTs and the low-temperature phase of the BKT problem are canonical examples. Along such a line, exponents can vary continuously.

Thus universality does not always mean “one small table of numbers.” It means the long-distance behavior is controlled by fixed-point data, which may include exactly marginal parameters.

## How universality is identified in practice

In real work, universality class identification is a triangulation problem.

### Step 1: Identify the order parameter and symmetries

Ask which symmetry is broken, which field becomes critical, and which sources couple to it. For an ordinary transition, this often gives the candidate Landau–Ginzburg action.

### Step 2: Determine the dimension and interaction range

The same symmetry in different dimensions can give different fixed points. Long-range interactions can replace $p^2$ by $p^\sigma$ in the quadratic action and change scaling.

### Step 3: List allowed relevant perturbations

Use symmetry and RG power counting to ask what must be tuned. If more parameters must be tuned than the experiment or model controls, the apparent criticality may be pre-asymptotic or fine-tuned.

### Step 4: Compare universal quantities

Critical exponents are the first comparison. Better tests use amplitude ratios, finite-size scaling functions, Binder cumulant crossings, operator spectra, OPE data, and universal conductivities or response coefficients when available.

### Step 5: Watch for crossover

A system may first look like one universality class and only later cross over to another. This happens when a relevant perturbation is small but nonzero. For example, weak anisotropy can produce a long approximate $O(N)$ scaling window before the true asymptotic class appears.

The RG picture is

$$
\text{microscopic model}
\longrightarrow
\text{near one fixed point}
\longrightarrow
\text{eventual fixed point or massive phase}.
$$

The first arrow may dominate finite experiments or simulations. The second arrow controls the mathematical asymptotic limit.

## Universality versus naturalness

Universality and naturalness are related but not identical.

Universality says that many irrelevant microscopic details do not affect long-distance critical behavior. Naturalness asks why relevant parameters are small enough to produce a large separation of scales. Near an Ising critical point, the temperature must be tuned close to $T_c$ to make $\xi$ large. The universal exponents do not explain why a material is close to criticality; they explain what happens once it is.

In statistical mechanics, a laboratory knob supplies the tuning. In particle physics, there may be no obvious external knob. This is why relevant scalar mass terms become naturalness problems in high-energy EFT while temperature tuning is mundane in a magnet.

The two lessons should not be confused:

$$
\text{universality explains insensitivity to irrelevant details},
$$

while

$$
\text{naturalness asks why relevant perturbations are small}.
$$

## Common pitfalls

**Thinking universality means microscopic equality.** Systems in the same universality class can have different atoms, lattices, interactions, and critical temperatures.

**Using symmetry alone as the classification.** Symmetry is crucial, but dimension, interaction range, relevant perturbations, topology, disorder, and conservation laws can change the class.

**Equating a universality class with a few exponents.** Exponents are only part of the fixed-point data. Scaling functions, amplitude ratios, operator spectra, OPE coefficients, and defect data can also be universal.

**Forgetting crossover.** Experiments and simulations may observe an intermediate scaling regime governed by a nearby fixed point rather than the ultimate asymptotic fixed point.

**Ignoring dangerously irrelevant variables.** An irrelevant coupling can still enter singular observables in a nontrivial way, especially above the upper critical dimension or in ordered phases.

**Assuming every transition is continuous.** A system may look nearly critical over a large window while ultimately being weakly first order. Walking RG flows and complex fixed points can make this especially treacherous.

## Relations to other pages

[Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/) introduces the Wilsonian idea that irrelevant details fade under coarse graining. This page specializes that idea to critical phenomena and fixed-point classification.

[Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) explains the objects that define universality classes. [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/) explains why relevant and irrelevant directions determine the basin structure. [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) and [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/) explain the most commonly measured universal data.

The next page, [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/), gives the canonical perturbative example of a nontrivial universality class below four dimensions.

## Research status

The basic RG definition of universality classes is established. The standard short-range $O(N)$ universality classes, the BKT transition, percolation-type classes, tricritical points, and many two-dimensional CFT universality classes are mature subjects.

Active research remains lively because modern systems often sit outside the simplest Landau–Ginzburg box. Important examples include deconfined criticality, conformal-bootstrap classification of fixed points, strongly disordered systems, long-range interacting systems, fractonic and subsystem-symmetric systems, non-Hermitian and nonequilibrium transitions, gauge-matter criticality, and topological or anomalous constraints on critical behavior.

A useful attitude is conservative but not timid. Universality is one of the deepest robust ideas in QFT, but identifying the correct universality class of a real or simulated system is often subtle.

## Exercises

### Exercise 1: Same exponents from the same fixed point

Suppose two microscopic systems have RG trajectories that approach the same fixed point. Near the fixed point they have the same thermal scaling eigenvalue $y_t$ and magnetic scaling eigenvalue $y_h$. Assuming ordinary hyperscaling, show that the two systems have the same exponents $\nu$, $\eta$, $\beta_{\mathrm{mag}}$, $\gamma$, and $\delta$.

<details><summary><strong>Solution</strong></summary>

The exponents are functions of the fixed-point eigenvalues and operator dimensions. In the notation used earlier in the chapter,

$$
\nu=\frac{1}{y_t},
\qquad
\eta=d+2-2y_h,
$$

and, assuming hyperscaling,

$$
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t},
\qquad
\gamma=\frac{2y_h-d}{y_t},
\qquad
\delta=\frac{y_h}{d-y_h}.
$$

If the two systems approach the same fixed point, then $d$, $y_t$, and $y_h$ are the same. Therefore these exponents are the same. Nonuniversal amplitudes can still differ because the microscopic variables can have different normalizations and metric factors.

</details>

### Exercise 2: Why tricriticality needs extra tuning

Consider a $\mathbb Z_2$-symmetric Landau potential

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4+\frac{v}{6!}\phi^6,
\qquad v>0.
$$

Explain why the ordinary critical point and tricritical point are not the same universality class.

<details><summary><strong>Solution</strong></summary>

For $u>0$, the ordinary continuous transition occurs by tuning $r$ to zero. The quartic interaction stabilizes the potential and the long-distance behavior is controlled by the ordinary scalar critical fixed point.

A tricritical point occurs when the quartic term is also tuned to zero:

$$
r=0,
\qquad u=0,
\qquad v>0.
$$

This requires an additional tuning. In RG language, the tricritical fixed point has a different set of relevant perturbations and different scaling dimensions. Therefore it defines a different universality class, even though the microscopic symmetry $\mathbb Z_2$ is the same.

</details>

### Exercise 3: Crossover from a weakly relevant perturbation

Let $u$ be a perturbation near a fixed point with small positive RG eigenvalue $y>0$. Under coarse graining by $b$, it scales as $u(b)=b^yu_0$. Estimate the crossover length scale $\xi_\times$ at which this perturbation becomes order one.

<details><summary><strong>Solution</strong></summary>

The perturbation becomes order one when

$$
b^y |u_0|\sim 1.
$$

Thus

$$
b_\times\sim |u_0|^{-1/y}.
$$

If the microscopic length is $a$, the crossover length is

$$
\xi_\times\sim a |u_0|^{-1/y}.
$$

For a weakly relevant perturbation, $y$ can be small, so $\xi_\times$ can be very large. A system may then show a long pre-asymptotic scaling regime controlled by the original fixed point before crossing over to the true infrared behavior.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., for the systematic QFT treatment of critical phenomena, RG, universality, and exponent calculations.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact introduction to universality, scaling, and critical phenomena.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for physical intuition and examples.
- Andrea Pelissetto and Ettore Vicari, "Critical phenomena and renormalization-group theory," *Physics Reports* **368** (2002) 549–727, for high-precision exponent data and universality-class surveys.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, 3rd ed., for universality, emergence, and matter examples.

## Version history

- 2026-06-17: First polished draft. Defined universality classes as RG basins of attraction, distinguished universal from nonuniversal data, and connected standard examples to fixed-point classification.
