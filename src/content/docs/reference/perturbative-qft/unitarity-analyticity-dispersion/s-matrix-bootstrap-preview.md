---
title: "S-Matrix Bootstrap Preview"
description: "A status-aware introduction to constraining scattering amplitudes from unitarity, analyticity, crossing, and low-energy data without assuming a Lagrangian."
sidebar:
  label: "S-Matrix Bootstrap Preview"
  order: 8
level: Advanced
status: "Polished draft"
source: "Eden et al.; Martin; Paulos et al.; Correia–Sever–Zhiboedov; Hebbar–Karateev–Penedones"
topics:
  - S-matrix bootstrap
  - analyticity
  - unitarity
  - crossing symmetry
  - scattering amplitudes
  - positivity bounds
canonicalTopics:
  - s-matrix-bootstrap
  - nonperturbative-s-matrix
  - analytic-unitarity-crossing-constraints
  - amplitude-space
researchStatus:
  established:
    - "The core constraints used in the S-matrix bootstrap — unitarity, crossing, analyticity, partial-wave bounds, and dispersion relations — are standard consequences of relativistic scattering theory under stated assumptions."
  active:
    - "Sharp nonperturbative bounds, spinning generalizations, massless limits, gravitational amplitudes, multiparticle constraints, and efficient numerical formulations remain active research directions."
---

## Summary

The **S-matrix bootstrap** asks how much of scattering theory follows from general consistency alone. Instead of starting from a Lagrangian and computing diagrams, one starts from the object that experiments directly probe — the scattering matrix — and imposes structural constraints:

$$
\text{unitarity}
+\text{crossing}
+\text{analyticity}
+\text{boundedness}
+\text{spectrum data}
\quad\Longrightarrow\quad
\text{allowed amplitudes}.
$$

The result is not usually a unique theory. More often, the bootstrap gives **bounds**: allowed ranges for couplings, scattering lengths, EFT coefficients, resonance parameters, partial waves, or low-energy amplitudes. In favorable cases, an extremal point of the allowed region behaves like an actual theory or a simple resonance model.

This page is a preview. It explains the logic and the assumptions, not a complete numerical implementation. The key lesson is simple but powerful: perturbation theory is optional; consistency of the S-matrix already knows a lot.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 54rem;">

![Flowchart of S-matrix bootstrap inputs, consistency constraints, allowed S-matrix space, and outputs such as EFT bounds and extremal amplitudes](/figures/perturbative-qft/s-matrix-bootstrap-preview.svg)

<figcaption>

The S-matrix bootstrap maps assumptions and low-energy data into an allowed region of amplitude space. Partial-wave unitarity, analyticity, crossing, and boundedness are not optional decorations; they are the constraints that make the problem rigid.

</figcaption>
</figure>

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/), [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/), [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/), and [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/). [Positivity Bounds Preview](/perturbative-qft/unitarity-analyticity-dispersion/positivity-bounds-preview/) is the closest sibling page.

## Core idea

A scattering amplitude can be studied as a function, not just as a sum of Feynman diagrams. In a relativistic QFT with stable asymptotic particles, a $2\to2$ amplitude depends on Mandelstam variables and is constrained by several independent facts:

| Constraint | What it says physically | What it does mathematically |
|---|---|---|
| Unitarity | probabilities add to one | bounds partial waves and relates imaginary parts to intermediate states |
| Crossing | incoming antiparticles can be moved to outgoing particles | relates different physical channels of one analytic function |
| Analyticity | causality and locality control singularities | restricts poles, cuts, and continuation between channels |
| Boundedness | high-energy growth is limited under assumptions | controls subtractions in dispersion relations |
| Spectrum data | masses and particle content are fixed inputs | locates thresholds and possible pole singularities |

The bootstrap uses these constraints as equations and inequalities. The amplitude is unknown, but not arbitrary.

## Setup and conventions

We use the scattering normalization of the Perturbative QFT volume:

$$
S_{fi}
=\delta_{fi}
+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}.
$$

For the cleanest preview, consider identical massive scalar particles of mass $m$ in four-dimensional flat spacetime. The elastic amplitude is

$$
\mathcal M(s,t),
\qquad
s+t+u=4m^2.
$$

For identical scalars, crossing symmetry relates the same analytic function evaluated in different channels. A fully symmetric amplitude satisfies

$$
\mathcal M(s,t)=\mathcal M(t,s)=\mathcal M(s,u),
$$

with the understanding that these equalities are statements about analytic continuation, not necessarily about a single real physical region.

The standard partial-wave expansion in the center-of-mass frame is

$$
\mathcal M(s,z)
=16\pi\sum_{\ell=0}^{\infty}(2\ell+1)a_\ell(s)P_\ell(z),
\qquad z=\cos\theta.
$$

For equal masses, define the phase-space-normalized partial wave

$$
\widehat a_\ell(s)=\rho(s)a_\ell(s),
\qquad
\rho(s)=\sqrt{1-\frac{4m^2}{s}}.
$$

In this normalization,

$$
S_\ell(s)=1+2i\widehat a_\ell(s).
$$

Partial-wave unitarity implies

$$
|S_\ell(s)|\leq 1
$$

when inelastic channels are allowed, and $|S_\ell|=1$ in a purely elastic region.

## Bootstrap problem

A typical bootstrap problem has three pieces.

First, choose the physical setting. For example: a gapped relativistic QFT, one stable scalar particle of mass $m$, no bound states below a specified threshold, and a chosen normalization of the low-energy expansion.

Second, choose the unknown data. One might parametrize a low-energy amplitude by EFT coefficients,

$$
\mathcal M(s,t)
= c_0+c_1(s^2+t^2+u^2)+c_2 stu+\cdots,
$$

or by pole residues, scattering lengths, phase shifts, or a basis of analytic functions. The specific basis is not physics; it is a computational representation of the physical constraints.

Third, optimize. A schematic problem might be

$$
\text{maximize } c_1
\quad\text{subject to unitarity, crossing, analyticity, and spectrum assumptions.}
$$

The output is an upper bound, lower bound, or allowed region. If the bound is sharp, the amplitude saturating it may contain useful information about a special theory, a resonance, or a limiting solution of the consistency constraints.

## Constraint one: unitarity

Unitarity is the most concrete constraint. For the normalized partial wave,

$$
S_\ell=1+2i\widehat a_\ell,
$$

so $|S_\ell|\leq1$ gives a disk in the complex $\widehat a_\ell$ plane:

$$
\left|1+2i\widehat a_\ell\right|\leq1.
$$

In an elastic region, one can write

$$
\widehat a_\ell(s)=e^{i\delta_\ell(s)}\sin\delta_\ell(s),
$$

where $\delta_\ell$ is the phase shift. In an inelastic region, the amplitude sits inside the disk rather than on the boundary.

At the level of the full amplitude, unitarity is nonlinear because imaginary parts contain products of amplitudes summed over intermediate states. Numerical bootstrap methods often make this manageable by working with partial waves, positive semidefinite matrices, or discretized inequalities.

## Constraint two: analyticity and singularities

Analyticity says that $\mathcal M(s,t)$ is the boundary value of a complex function with singularities controlled by physical intermediate states. Poles correspond to stable particles or bound states. Branch cuts begin at multiparticle thresholds.

In the $s$ channel, the discontinuity across a cut is

$$
\operatorname{Disc}_s\mathcal M(s,t)
=\mathcal M(s+i0,t)-\mathcal M(s-i0,t).
$$

For forward scattering, the optical theorem relates the imaginary part to a total cross section. Schematically,

$$
\operatorname{Im}\mathcal M(s,0)\geq0
$$

in the physical region, with normalization-dependent positive factors omitted here because the sign is the important point.

Analyticity is powerful but also delicate. The strongest bootstrap claims usually require assumptions such as a mass gap, polynomial boundedness, and some version of Mandelstam analyticity. These are physically motivated and widely used, but they are not trivial theorems for every QFT in every dimension.

## Constraint three: crossing

Crossing symmetry prevents one from building a good-looking amplitude in one channel that contradicts another channel. For identical scalars, the $s$-, $t$-, and $u$-channel descriptions must be analytic continuations of the same object.

This is what turns a collection of inequalities into a bootstrap. Unitarity alone constrains physical partial waves in one channel. Crossing ties those constraints to other kinematic regions, including regions where different partial-wave decompositions apply.

A crude but useful slogan is:

$$
\text{unitarity gives positivity; crossing spreads it around.}
$$

## What the bootstrap can give

The S-matrix bootstrap can be used in several modes.

| Use | Typical output | Caveat |
|---|---|---|
| Low-energy EFT bounds | inequalities for Wilson coefficients | assumptions about UV completion and mass gap matter |
| Resonance constraints | allowed masses, widths, residues, or phase shifts | model-independent bounds are usually weaker than model fits |
| Nonperturbative amplitude bounds | allowed regions in coupling space | numerical truncations require convergence checks |
| Extremal amplitudes | candidate amplitudes saturating bounds | saturation does not automatically prove existence of a local QFT |
| Connections to CFT bootstrap | flat-space limits or AdS-inspired formulations | dictionary and limits can be technically subtle |

This page sits at the interface of positivity bounds, partial-wave unitarity, dispersion theory, and modern numerical amplitude methods.

## Relation to positivity bounds

Positivity bounds are a controlled corner of the S-matrix bootstrap. In a gapped theory, a forward-limit dispersion relation often gives a positive integral over a physical cross section, leading to inequalities such as

$$
\frac{\partial^2}{\partial s^2}\mathcal M(s,0)\Big|_{s=s_0}>0
$$

for appropriate subtraction point $s_0$ and after removing known pole contributions.

The full S-matrix bootstrap asks for more. It may use nonforward kinematics, partial-wave unitarity, crossing-symmetric ansatzes, finite-energy constraints, spin, or numerical optimization over functions. Positivity bounds are therefore not separate from the bootstrap; they are one of its most transparent analytic limits.

## Common pitfalls

**Thinking the bootstrap needs no assumptions.** The bootstrap is assumption-light, not assumption-free. Mass gaps, asymptotic states, analyticity domains, high-energy boundedness, crossing properties, and spectrum assumptions all matter.

**Confusing allowed amplitudes with realized theories.** A function can satisfy many S-matrix constraints without a known local QFT construction behind it. Showing consistency of an amplitude is not always the same as constructing the theory.

**Using perturbative intuition for nonperturbative bounds.** Perturbative diagrams are examples inside the allowed space, not the definition of the allowed space. Bootstrap bounds may apply even when no small coupling expansion is available.

**Ignoring truncation errors.** Numerical implementations use finite bases, finite spin cutoffs, grids, or semidefinite relaxations. A sharp-looking plot is trustworthy only after stability and convergence tests.

**Forgetting massless and gravitational subtleties.** Long-range forces, IR divergences, soft radiation, and massless thresholds can invalidate assumptions that are harmless in a gapped scalar example.

## Relations to other pages

- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) derives the basic unitarity relation behind positivity of absorptive parts.
- [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) explains perturbative discontinuities, which are the diagrammatic shadow of unitarity.
- [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/) gives the analytic machinery behind many bootstrap inequalities.
- [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/) gives the angular-momentum unitarity disk used in many numerical formulations.
- [Positivity Bounds Preview](/perturbative-qft/unitarity-analyticity-dispersion/positivity-bounds-preview/) is the closest analytic entry point into bootstrap-style EFT constraints.
- [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) introduces the on-shell variables used in many spinning amplitude bootstrap problems.

## Research status

The basic constraints are textbook scattering theory. The modern S-matrix bootstrap is an active program that tries to make these constraints quantitatively sharp, especially in dimensions higher than two and for particles with spin.

The cleanest successes occur in settings with a mass gap and controlled analytic assumptions. Open directions include efficient treatment of multiparticle unitarity, massless particles, gravity, gauge theories with confinement, spinning amplitudes, numerical convergence, and the relation between allowed amplitudes and actual QFT constructions.

## Exercises

### Exercise 1: The unitarity disk

Starting from $S_\ell=1+2i\widehat a_\ell$, show that $|S_\ell|\leq1$ implies

$$
\left(\operatorname{Re}\widehat a_\ell\right)^2
+\left(\operatorname{Im}\widehat a_\ell-\frac12\right)^2
\leq \frac14.
$$

<details>
<summary><strong>Solution</strong></summary>

Write $\widehat a_\ell=x+iy$. Then

$$
S_\ell=1+2i(x+iy)=1-2y+2ix.
$$

Therefore

$$
|S_\ell|^2=(1-2y)^2+4x^2\leq1.
$$

Expanding and dividing by $4$ gives

$$
x^2+y^2-y\leq0,
$$

or

$$
x^2+\left(y-\frac12\right)^2\leq\frac14.
$$

</details>

### Exercise 2: Elastic phase shifts

Assume $|S_\ell|=1$ and write $S_\ell=e^{2i\delta_\ell}$. Show that

$$
\widehat a_\ell=e^{i\delta_\ell}\sin\delta_\ell.
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\widehat a_\ell=\frac{S_\ell-1}{2i}
=\frac{e^{2i\delta_\ell}-1}{2i}.
$$

Factor out $e^{i\delta_\ell}$:

$$
e^{2i\delta_\ell}-1
=e^{i\delta_\ell}\left(e^{i\delta_\ell}-e^{-i\delta_\ell}\right)
=2i e^{i\delta_\ell}\sin\delta_\ell.
$$

Thus

$$
\widehat a_\ell=e^{i\delta_\ell}\sin\delta_\ell.
$$

</details>

### Exercise 3: Crossing-symmetric polynomial

For identical scalars with $s+t+u=4m^2$, check that

$$
s^2+t^2+u^2
$$

is crossing symmetric.

<details>
<summary><strong>Solution</strong></summary>

Crossing for identical scalars permutes $s$, $t$, and $u$. The expression

$$
s^2+t^2+u^2
$$

is symmetric under all permutations of the three variables, so it is crossing symmetric. The constraint $s+t+u=4m^2$ is not needed for this particular check, but it is used when choosing an independent basis of low-energy polynomials.

</details>

### Exercise 4: Positivity as a bootstrap shadow

Explain in one paragraph why a forward-limit positivity bound can be viewed as a small part of the S-matrix bootstrap.

<details>
<summary><strong>Solution</strong></summary>

A forward-limit positivity bound uses analyticity to write a low-energy coefficient as a dispersion integral and uses unitarity, through the optical theorem, to make the integrand positive. This is already a bootstrap argument: a low-energy parameter is constrained by consistency of the full S-matrix. The full S-matrix bootstrap keeps more information, such as nonforward kinematics, crossing, partial-wave unitarity, spin, and sometimes numerical optimization over larger amplitude spaces.

</details>

## References

### Standard first pass

- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for the classic analytic S-matrix framework.
- A. Martin, *Scattering Theory: Unitarity, Analyticity and Crossing*, for rigorous scattering-theory constraints.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering theory, unitarity, partial waves, and resonances.

### Modern bootstrap and positivity

- M. Kruczenski, J. Penedones, and B. C. van Rees, “Snowmass White Paper: S-matrix Bootstrap,” for a compact overview of the modern numerical program and its open directions.
- M. F. Paulos, J. Penedones, J. Toledo, B. C. van Rees, and P. Vieira, “The S-matrix Bootstrap III: Higher Dimensional Amplitudes,” for numerical higher-dimensional amplitude bounds.
- M. Correia, A. Sever, and A. Zhiboedov, “An Analytical Toolkit for the S-matrix Bootstrap,” for analytic constraints, large spin, threshold expansions, and bootstrap methodology.
- A. Hebbar, D. Karateev, and J. Penedones, “Spinning S-matrix Bootstrap in 4d,” for spinning generalizations.
- A. Adams, N. Arkani-Hamed, S. Dubovsky, A. Nicolis, and R. Rattazzi, “Causality, Analyticity and an IR Obstruction to UV Completion,” for EFT positivity-bound logic.

## Version history

- **2026-06-13:** Initial standardized page.
