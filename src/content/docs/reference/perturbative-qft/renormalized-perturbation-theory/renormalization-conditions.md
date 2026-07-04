---
title: "Renormalization Conditions"
description: "How renormalization conditions fix the finite and divergent parts of counterterms by specifying selected Green functions, 1PI vertices, pole data, or amplitudes."
sidebar:
  label: "Renormalization Conditions"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20 and 27–28; Coleman 2019, chs. 15–16 and 25; Weinberg 1995, Vol. I, chs. 10 and 12; Schwartz 2014, chs. 18–21; Zinn-Justin 2021, chs. 9–10"
topics:
  - renormalization conditions
  - subtraction schemes
  - counterterms
  - momentum subtraction
  - on-shell renormalization
canonicalTopics:
  - renormalization-condition
  - subtraction-scheme
  - counterterm-fixing
  - momentum-subtraction
  - scheme-dependence
researchStatus:
  established:
    - "Renormalization conditions are the standard way to fix counterterms: they specify finite values of selected renormalized Green functions, 1PI vertices, residues, masses, or amplitudes."
  active:
    - "In precision gauge theories and EFTs, choosing stable and symmetry-compatible renormalization conditions remains technically important, especially with massless particles, unstable particles, operator mixing, and multiple scales."
---

## Summary

A **renormalization condition** is a rule that fixes the counterterms by specifying what selected renormalized quantities must equal at selected kinematic points. It turns the formal split

$$
\mathcal L_0=\mathcal L_{\rm ren}+\mathcal L_{\rm ct}
$$

into a concrete calculation scheme.

For a scalar field with self-energy convention

$$
G_{\rm ren}(p)=\frac{i}{p^2-m^2-\Sigma_{\rm ren}(p^2)+i\epsilon},
$$

a common pair of two-point conditions is

$$
\Sigma_{\rm ren}(s_*)=0,
\qquad
\Sigma_{\rm ren}'(s_*)=0.
$$

The chosen subtraction point $s_*$ may be a physical pole, as in an on-shell scheme, or a Euclidean momentum point, as in momentum subtraction. The conditions fix the mass and field-strength counterterms. Additional conditions fix couplings and vacuum-energy counterterms.

The important lesson is simple: divergent loop integrals do not determine a unique finite answer by themselves. A regulator plus counterterms plus renormalization conditions define the finite coordinates used for predictions.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Flow chart showing renormalization conditions fixing counterterms from loop corrections to finite two-point and four-point functions](/figures/perturbative-qft/renormalization-conditions.svg)

<figcaption>

Renormalization conditions select finite values of chosen Green functions or amplitudes. The loop corrections determine which counterterms are needed; the conditions fix their divergent and finite pieces within the chosen scheme.

</figcaption>
</figure>

## Prerequisites

You should know [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/), [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/), [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/), and [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/).

For the scattering interpretation of pole residues, review [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) and [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/).

## Core idea

Counterterms have two jobs. Their divergent pieces cancel regulator dependence. Their finite pieces define the meaning of the renormalized parameters.

A renormalization condition is the sentence that gives those finite pieces a job. It may say, for example, “the propagator has a pole at this mass,” “the pole residue is one,” “the four-point vertex equals $-i\lambda$ at this momentum point,” or “only poles in $\epsilon$ are subtracted.” Different conditions define different coordinate systems on the same physical predictions.

The conceptual chain is

$$
\text{loop corrections}
\quad + \quad
\text{counterterms}
\quad + \quad
\text{conditions}
\quad \Longrightarrow \quad
\text{finite renormalized quantities}.
$$

The conditions are not extra dynamics. They are definitions of the renormalized mass, field normalization, coupling, and other parameters.

## Setup and conventions

We use qft.org mostly-minus conventions, the Fourier phase $e^{-ip\cdot x}$, and the scalar self-energy convention

$$
\text{1PI two-point insertion}=-i\Sigma(p^2).
$$

For scalar counterterms,

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2,
$$

so the counterterm contribution to the self-energy is

$$
\Sigma_{\rm ct}(p^2)=\delta m^2-\delta Z\,p^2.
$$

Thus

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Z\,p^2.
$$

The inverse renormalized propagator is

$$
\Gamma_{\rm ren}^{(2)}(p^2)
=
p^2-m^2-\Sigma_{\rm ren}(p^2).
$$

These formulas are convention-sensitive. They match the self-energy and counterterm conventions used in the previous pages of this chapter.

## What a renormalization condition fixes

A renormalizable scalar theory in four dimensions has a finite number of independent local counterterms. For the real scalar example, the usual set is

$$
\delta Z,
\qquad
\delta m^2,
\qquad
\delta\lambda,
\qquad
\delta\Lambda.
$$

A condition is needed for each independent coefficient that affects the quantities being computed. The conditions must be independent. Asking the same Green function the same question twice does not fix a new counterterm.

A useful map is:

| Counterterm | Typical condition | Physical meaning |
|---|---|---|
| $\delta m^2$ | position of a two-point pole or value of $\Gamma^{(2)}$ at a subtraction point | defines the renormalized mass parameter |
| $\delta Z$ | derivative of $\Gamma^{(2)}$ or pole residue | defines the renormalized field normalization |
| $\delta\lambda$ | four-point vertex or scattering amplitude at a chosen point | defines the renormalized coupling |
| $\delta\Lambda$ | vacuum functional or vacuum energy condition | defines the zero of vacuum energy |

The last entry is often invisible in ordinary flat-space scattering because normalized correlators cancel vacuum bubbles. It becomes visible when one computes the effective action, vacuum energy, finite-temperature free energy, or gravity-coupled observables.

## Two-point conditions

Suppose the loop self-energy has already been computed. Choose a subtraction point

$$
s_*=p_*^2.
$$

A common condition is that the renormalized inverse propagator and its first derivative match the tree-level form at $s_*$. Equivalently,

$$
\Sigma_{\rm ren}(s_*)=0,
\qquad
\Sigma_{\rm ren}'(s_*)=0.
$$

Substituting

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Z\,p^2
$$

gives

$$
0=\Sigma_{\rm loop}'(s_*)-\delta Z,
$$

so

$$
\delta Z=\Sigma_{\rm loop}'(s_*).
$$

The value condition then gives

$$
0=\Sigma_{\rm loop}(s_*)+\delta m^2-s_*\delta Z,
$$

hence

$$
\delta m^2=-\Sigma_{\rm loop}(s_*)+s_*\Sigma_{\rm loop}'(s_*).
$$

If $s_*=M^2$ is the physical pole and one takes real parts, these are on-shell-type conditions. If $s_*=-\mu^2$ is Euclidean and spacelike, these are momentum-subtraction-type conditions.

:::caution[Subtraction point versus physical point]
The subtraction point is part of the parameter definition. It need not be a physical momentum configuration. Euclidean subtraction points are often chosen precisely because they avoid thresholds, cuts, and infrared singularities.
:::

## Coupling conditions

A mass and field normalization do not fix the coupling. For scalar $\phi^4$ theory, define the reduced renormalized four-point 1PI vertex $\mathcal V_{\rm ren}^{(4)}$ by

$$
V_{\rm ren}^{(4)}=-i\mathcal V_{\rm ren}^{(4)}.
$$

At tree level,

$$
\mathcal V_{\rm tree}^{(4)}=\lambda.
$$

A momentum-subtraction condition chooses a kinematic point $\mathcal P_*$ and requires

$$
\mathcal V_{\rm ren}^{(4)}(\mathcal P_*)=\lambda.
$$

For a massive theory, $\mathcal P_*$ is often chosen to be a Euclidean symmetric point so that no channel is at threshold. For example, one may choose external momenta satisfying

$$
p_i^2=-\mu^2,
\qquad
\sum_{i=1}^4p_i=0,
$$

with all pairwise invariants fixed symmetrically. The exact symmetric convention varies by source and theory, but the purpose is the same: define the coupling by a finite local normalization of the four-point function.

If the loop contribution to the reduced vertex is $\mathcal V_{\rm loop}^{(4)}$ and the counterterm contribution is $\delta\lambda$, then schematically

$$
\mathcal V_{\rm ren}^{(4)}
=
\lambda+\mathcal V_{\rm loop}^{(4)}+\delta\lambda.
$$

The condition at $\mathcal P_*$ gives

$$
\delta\lambda=-\mathcal V_{\rm loop}^{(4)}(\mathcal P_*).
$$

This equation hides a lot of practical work: the loop contribution includes regulator poles, finite logarithms, and momentum-dependent terms. The counterterm cancels only the local value demanded by the condition; nonlocal momentum dependence remains in the renormalized vertex.

## Common schemes as conditions

The word “scheme” means a whole set of renormalization conditions. Four common styles are:

| Scheme | Conditions | Strength | Caveat |
|---|---|---|---|
| On-shell | Poles, residues, and selected physical amplitudes match physical values. | Direct physical interpretation for stable particles. | Awkward with massless particles, unstable particles, confinement, and large logarithms. |
| Momentum subtraction | Green functions match chosen values at fixed external momenta. | Concrete and useful for nonzero Euclidean scales. | Gauge and infrared subtleties require careful choices. |
| Minimal subtraction | Counterterms remove only $1/\epsilon$ poles. | Simple RG equations and multi-loop bookkeeping. | Parameters are not directly physical observables. |
| Modified minimal subtraction | Counterterms remove the standard $1/\overline\epsilon$ combination. | The most common perturbative convention in many continuum calculations. | Still a convention; finite conversions are needed to compare to physical schemes. |

The on-shell and momentum-subtraction cases are conditions on finite Green functions. Minimal subtraction is also a renormalization condition, but it is a condition on the pole part of the counterterm rather than on the finite value of a physical observable.

## Scheme dependence and physical independence

Changing renormalization conditions changes the renormalized parameters. It does not change the underlying physical prediction when all orders are included and the same physical inputs are used.

At finite perturbative order, different schemes can give numerically different approximations. This is not a contradiction. Truncating the series leaves residual scheme and scale dependence, and this residual dependence is often used as one diagnostic of missing higher-order terms.

For a coupling, a finite scheme change has the schematic form

$$
\lambda'=\lambda+a\lambda^2+b\lambda^3+\cdots.
$$

The same amplitude can be written in either coordinate. The coefficients in the perturbative expansion change, but the all-order function does not.

## Choosing good conditions

Good renormalization conditions are not merely mathematically valid. They are adapted to the physics and the computation.

A good set of conditions should be:

1. **sufficient**, fixing all counterterms needed for the calculation;
2. **independent**, so each condition fixes a genuinely different parameter;
3. **symmetry-compatible**, preserving gauge symmetry, global symmetries, Lorentz symmetry, and discrete symmetries when required;
4. **infrared-safe**, avoiding accidental singularities from massless particles or thresholds;
5. **practical**, minimizing large logarithms and unnecessary finite conversions.

No scheme is universally best. On-shell conditions are natural for stable-particle pole observables. Minimal subtraction is natural for RG evolution and high-order loop work. Momentum subtraction is useful when one wants a physically concrete finite normalization at a chosen scale.

## Checks

A renormalized calculation should pass several checks.

**Regulator cancellation.** After loop diagrams and counterterm diagrams are combined, the chosen renormalized quantity should be finite as the regulator is removed.

**Condition satisfaction.** The final renormalized Green function or amplitude should actually obey the imposed condition. This sounds silly until one has lost a sign in a counterterm.

**Symmetry preservation.** Conditions in gauge theories must be compatible with Ward, Slavnov–Taylor, or BRST identities. Otherwise the subtraction can manufacture symmetry-violating artifacts.

**Physical invariance.** If two schemes are related by finite redefinitions, properly converted predictions for physical observables should agree order by order up to higher-order truncation errors.

## Common pitfalls

**Thinking counterterms are fixed by divergences alone.** Divergences fix only the pieces needed for finiteness. The finite pieces are fixed by the renormalization conditions, so the same divergent loop integral can lead to different finite renormalized expressions in different schemes.

**Imposing conditions at singular kinematics.** Exceptional momenta, thresholds, and massless limits can introduce infrared singularities unrelated to UV renormalization. Choose subtraction points that do not confuse UV subtraction with long-distance physics.

**Forgetting field normalization.** Fixing the pole location fixes a mass parameter, not the residue. A separate derivative condition is needed if the renormalized field is to create a one-particle state with unit residue.

**Violating symmetries by subtraction.** Counterterms and conditions must respect the theory's symmetries unless the symmetry is genuinely anomalous or explicitly broken. Gauge-theory renormalization is especially unforgiving about this.

**Comparing parameters across schemes as if they were observables.** The number called $m$ or $\lambda$ is not meaningful without a definition. Compare pole masses, cross sections, decay rates, or explicitly converted scheme parameters.

## Relations to other pages

- [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/) explains the parameter split that renormalization conditions make concrete.
- [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/) derives the local counterterm vertices whose coefficients are fixed by the conditions here.
- [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/) specializes these ideas to pole masses, residues, and physical amplitudes.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) provides the two-point function convention used in the examples.
- [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) explains the loop corrections whose finite values define coupling counterterms.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) connects field-strength conditions to scattering amplitudes and LSZ residues.

## Research status

The logic of renormalization conditions is textbook-standard. The main subtleties are not conceptual but technical: gauge-compatible schemes, finite scheme conversions, unstable-particle prescriptions, evanescent operators, operator mixing, infrared-safe definitions, and multi-scale processes. Those issues become essential in precision Standard Model, EFT, and multi-loop calculations.

## Exercises

### Exercise 1: Fixing two-point counterterms

Assume

$$
\Sigma_{\rm ren}(p^2)=\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2.
$$

Impose

$$
\Sigma_{\rm ren}(s_*)=0,
\qquad
\Sigma_{\rm ren}'(s_*)=0.
$$

Derive $\delta Z$ and $\delta m^2$.

<details>
<summary><strong>Solution</strong></summary>

The derivative condition gives

$$
0=\Sigma_{\rm loop}'(s_*)-\delta Z,
$$

so

$$
\delta Z=\Sigma_{\rm loop}'(s_*).
$$

The value condition gives

$$
0=\Sigma_{\rm loop}(s_*)+\delta m^2-s_*\delta Z.
$$

Substituting the value of $\delta Z$ gives

$$
\delta m^2=-\Sigma_{\rm loop}(s_*)+s_*\Sigma_{\rm loop}'(s_*).
$$

</details>

### Exercise 2: Residue from the inverse propagator

Let

$$
\Gamma_{\rm ren}^{(2)}(p^2)=p^2-m^2-\Sigma_{\rm ren}(p^2).
$$

Show that if

$$
\Gamma_{\rm ren}^{(2)}(M^2)=0,
\qquad
\frac{d\Gamma_{\rm ren}^{(2)}}{dp^2}\bigg|_{p^2=M^2}=1,
$$

then the propagator has unit residue at $p^2=M^2$.

<details>
<summary><strong>Solution</strong></summary>

Near the pole,

$$
\Gamma_{\rm ren}^{(2)}(p^2)
=
\Gamma_{\rm ren}^{(2)}(M^2)
+(p^2-M^2)\Gamma_{\rm ren}^{(2)\prime}(M^2)+\cdots.
$$

The first condition sets the first term to zero. The second condition sets the coefficient of $p^2-M^2$ to one. Therefore

$$
\Gamma_{\rm ren}^{(2)}(p^2)=p^2-M^2+\cdots,
$$

and

$$
G_{\rm ren}(p)=\frac{i}{\Gamma_{\rm ren}^{(2)}(p^2)+i\epsilon}
\sim
\frac{i}{p^2-M^2+i\epsilon}.
$$

The coefficient of the pole is one.

</details>

### Exercise 3: Coupling counterterm at a subtraction point

Let the reduced four-point vertex be

$$
\mathcal V_{\rm ren}^{(4)}(\mathcal P)
=\lambda+\mathcal V_{\rm loop}^{(4)}(\mathcal P)+\delta\lambda.
$$

Impose

$$
\mathcal V_{\rm ren}^{(4)}(\mathcal P_*)=\lambda.
$$

Find $\delta\lambda$.

<details>
<summary><strong>Solution</strong></summary>

At the subtraction point,

$$
\lambda+\mathcal V_{\rm loop}^{(4)}(\mathcal P_*)+\delta\lambda=\lambda.
$$

Therefore

$$
\delta\lambda=-\mathcal V_{\rm loop}^{(4)}(\mathcal P_*).
$$

This equation includes both divergent and finite pieces in a momentum-subtraction scheme.

</details>

### Exercise 4: Minimal subtraction as a condition

Suppose a loop correction contains

$$
\mathcal V_{\rm loop}^{(4)}
=\frac{A}{\epsilon}+B(\mathcal P)+O(\epsilon).
$$

What counterterm is chosen in minimal subtraction, and why does the finite function $B(\mathcal P)$ remain?

<details>
<summary><strong>Solution</strong></summary>

In minimal subtraction one chooses

$$
\delta\lambda=-\frac{A}{\epsilon},
$$

up to signs fixed by the precise reduced-vertex convention. The condition is to remove the pole part only. The finite part $B(\mathcal P)$ is not subtracted because minimal subtraction does not impose a finite value of the vertex at a physical or Euclidean momentum point.

The renormalized vertex therefore keeps finite momentum dependence. That finite dependence is part of the prediction in the chosen scheme.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§14–20 and 27–28, for self-energies, vertex corrections, perturbation theory to all orders, and scheme dependence.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 25, for counterterm determination and the logic of renormalization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 18–21, for mass renormalization, counterterms, renormalized perturbation theory, and renormalizability.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 10 and 12, for systematic renormalization and the structure of counterterms.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 9–10, for renormalized QFT, dimensional regularization, and minimal subtraction from the field-theoretic RG viewpoint.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. III.3, for a compact physical discussion of counterterms and renormalized perturbation theory.

## Version history

- **2026-06-12:** Initial standardized page.
