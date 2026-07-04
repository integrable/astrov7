---
title: "On-Shell Scheme"
description: "How the on-shell renormalization scheme defines masses, residues, and selected couplings by physical pole and scattering conditions."
sidebar:
  label: "On-Shell Scheme"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–16 and 25–27; Coleman 2019, chs. 15–17 and 25; Weinberg 1995, Vol. I, chs. 10 and 12; Schwartz 2014, chs. 18–20; Zee 2010, ch. III.3"
topics:
  - on-shell scheme
  - pole mass
  - wavefunction renormalization
  - physical renormalization scheme
  - residue conditions
canonicalTopics:
  - on-shell-renormalization
  - pole-mass
  - residue-condition
  - physical-renormalization-scheme
  - mass-renormalization
researchStatus:
  established:
    - "The on-shell scheme is a standard physical renormalization scheme for stable particles: renormalized masses are fixed by pole locations, field normalizations by pole residues, and couplings by selected physical amplitudes."
  active:
    - "For gauge theories, unstable particles, massless charged particles, confinement, and high-precision multi-scale observables, on-shell definitions require careful infrared, gauge-invariance, and complex-pole treatments."
---

## Summary

The **on-shell scheme** defines renormalized parameters using physical on-shell data. For a stable scalar particle, the renormalized mass is chosen to be the pole mass, and the renormalized field is chosen so that the pole residue is one:

$$
G_{\rm ren}(p)
\sim
\frac{i}{p^2-M^2+i\epsilon}
\quad\text{near }p^2=M^2.
$$

With the scalar self-energy convention

$$
G_{\rm ren}(p)=\frac{i}{p^2-M^2-\Sigma_{\rm ren}(p^2)+i\epsilon},
$$

the on-shell two-point conditions are

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

The first condition fixes the pole position. The second fixes the residue of the renormalized field. Couplings are fixed by additional physical conditions, such as a threshold scattering amplitude or, in QED, the low-energy electric charge.

The on-shell scheme is physically transparent. Its price is that it is tied to particles that actually have well-defined on-shell states. That makes it less universal than mass-independent schemes in massless gauge theories, strongly coupled theories, EFT matching, and high-energy multi-scale calculations.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![The on-shell scheme fixes the pole position, unit residue, and a physical coupling normalization from selected on-shell data](/figures/perturbative-qft/on-shell-scheme.svg)

<figcaption>

In the on-shell scheme, the inverse propagator vanishes at the physical mass and has unit slope there. Couplings require additional physical normalization conditions, such as a scattering amplitude or low-energy charge definition.

</figcaption>
</figure>

## Prerequisites

You should know [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/), [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/), [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/), and [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/).

For cross sections and decay widths, review [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) and [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/).

## Core idea

The on-shell scheme names parameters by what a detector would call them in an ideal stable-particle experiment.

The mass parameter is not defined by a coefficient in the bare Lagrangian. It is defined by the pole of the renormalized propagator. The field normalization is not defined by an arbitrary kinetic coefficient. It is fixed by the residue of that pole. A coupling is not defined by a formal symbol in a Lagrangian. It is fixed by a selected physical amplitude.

The slogan is

$$
\text{on-shell scheme}=
\text{renormalized parameters defined by physical pole and amplitude data}.
$$

That slogan is most reliable for massive stable particles in theories without severe infrared complications. When the theory contains massless gauge bosons, unstable particles, or confined fields, the same words require more care.

## Setup and conventions

We use the scalar self-energy convention

$$
\text{1PI two-point insertion}=-i\Sigma(p^2),
$$

and the quadratic counterterm convention

$$
\Sigma_{\rm ct}(p^2)=\delta m^2-\delta Zp^2.
$$

For this page, choose the renormalized mass parameter $m$ to equal the physical pole mass $M$ order by order:

$$
m=M.
$$

Then

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2.
$$

If the self-energy has an imaginary part at the pole, the stable-particle on-shell conditions must be modified. Below we first treat the stable-particle case, where the real pole and its residue are the appropriate objects.

## Scalar on-shell conditions

The resummed scalar propagator is

$$
G_{\rm ren}(p)
=
\frac{i}{p^2-M^2-\Sigma_{\rm ren}(p^2)+i\epsilon}.
$$

The pole should occur at

$$
p^2=M^2.
$$

Therefore the denominator must vanish there:

$$
M^2-M^2-\operatorname{Re}\Sigma_{\rm ren}(M^2)=0.
$$

This gives the mass condition

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0.
$$

The residue condition is obtained by expanding near the pole. Let

$$
D(p^2)=p^2-M^2-\Sigma_{\rm ren}(p^2).
$$

Then

$$
D(p^2)
=(p^2-M^2)\left[1-\Sigma_{\rm ren}'(M^2)\right]+\cdots.
$$

The propagator therefore behaves as

$$
G_{\rm ren}(p)
\sim
\frac{i}{(p^2-M^2)\left[1-\Sigma_{\rm ren}'(M^2)\right]+i\epsilon}.
$$

To make the residue equal to one, impose

$$
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

Equivalently, in terms of the inverse two-point function

$$
\Gamma_{\rm ren}^{(2)}(p^2)=p^2-M^2-\Sigma_{\rm ren}(p^2),
$$

the on-shell conditions are

$$
\Gamma_{\rm ren}^{(2)}(M^2)=0,
\qquad
\frac{d\Gamma_{\rm ren}^{(2)}}{dp^2}\bigg|_{p^2=M^2}=1.
$$

This form is often the cleanest because it says directly what happens to the inverse propagator.

## Counterterms in the scalar on-shell scheme

Using

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2,
$$

the derivative condition gives

$$
0=\operatorname{Re}\Sigma_{\rm loop}'(M^2)-\delta Z.
$$

Therefore

$$
\delta Z=\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

The value condition gives

$$
0=\operatorname{Re}\Sigma_{\rm loop}(M^2)+\delta m^2-M^2\delta Z.
$$

Therefore

$$
\delta m^2
=-\operatorname{Re}\Sigma_{\rm loop}(M^2)
+M^2\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

These formulas include both divergent and finite pieces. The finite pieces are exactly what distinguish the on-shell scheme from minimal subtraction.

:::note[Why the real part?]
For a stable particle below all decay thresholds, the self-energy is real at the pole. If a decay channel is open, the pole moves away from the real axis and the correct definition uses a complex pole. Taking only a real on-shell condition is then an approximation or a convention that must be justified.
:::

## Coupling conditions

Mass and residue conditions do not define the interaction strength. A coupling requires an additional normalization condition.

In scalar $\phi^4$ theory, one may define the on-shell coupling by a physical $2\to2$ amplitude. At tree level the amplitude is

$$
\mathcal M_{\rm tree}=-\lambda.
$$

A simple massive-scalar condition is

$$
\mathcal M_{\rm ren}(s=4M^2,t=0,u=0)=-\lambda_{\rm OS},
$$

where the point is the two-particle threshold for identical scalars. In other theories, especially those with massless exchange or threshold singularities, a different physical point or infrared-safe observable may be a better definition.

The general pattern is:

| Parameter | On-shell definition |
|---|---|
| mass | pole location of the propagator |
| field normalization | residue of the stable one-particle pole |
| coupling | selected physical amplitude or low-energy observable |
| vacuum energy | selected vacuum-energy convention, if needed |

The on-shell scheme is therefore not only a two-point scheme. It is a physical normalization of the whole set of parameters used in the calculation.

## External legs and LSZ

LSZ reduction says that scattering amplitudes are obtained from time-ordered correlators by taking residues at one-particle poles. If the renormalized field has pole residue $Z$, the LSZ reduction formula supplies a factor $Z^{-1/2}$ for each external scalar leg when starting from the corresponding Green function.

The on-shell field-strength condition sets the renormalized pole residue to one:

$$
Z_{\rm pole}=1.
$$

This is why on-shell schemes are convenient for scattering calculations with stable external particles: explicit finite residue corrections are absorbed into the counterterm definition of the renormalized field.

This statement is not a license to ignore external-leg physics. It says that, after the on-shell residue condition is imposed, the LSZ residue is already normalized in the chosen renormalized field. In another scheme, the residue generally differs from one and must be accounted for when relating Green functions to S-matrix elements.

## QED as a standard example

In QED, the on-shell scheme is usually described by physical electron and photon data.

For the electron, the mass is fixed by the pole of the fermion propagator. Schematically,

$$
S_{\rm ren}(p)
\sim
\frac{i}{p\!\!\!/-m_{\rm e}+i\epsilon}
$$

near the pole, with unit residue in the renormalized field convention. Here

$$
p\!\!\!/\equiv\gamma^\mu p_\mu.
$$

For the photon, gauge invariance keeps the photon massless. The electric charge is fixed by a physical low-energy normalization, often described as the Thomson limit: the electron–photon vertex at zero momentum transfer reproduces the measured electric charge. Ward–Takahashi identities then tie the vertex and electron field renormalizations together.

There is a subtle but important caveat. Because the photon is massless, charged asymptotic states in exact QED have infrared structure beyond the simple massive-particle pole picture. The on-shell scheme remains a standard perturbative convention, but physical predictions must be formulated for infrared-safe inclusive observables.

## Comparison with minimal subtraction

The on-shell scheme and minimal subtraction answer different practical needs.

| Feature | On-shell scheme | Minimal subtraction |
|---|---|---|
| Mass parameter | pole mass for stable particles | running scheme parameter |
| Residue | usually fixed to one | generally not one |
| Counterterm finite parts | fixed by physical conditions | not fixed except by pole-subtraction convention |
| RG simplicity | less simple in multi-scale problems | very simple |
| Physical transparency | high for stable particles | indirect; requires conversion |
| Best use | precision around physical masses and low-energy observables | high-order loops, RG running, EFT matching |

Neither scheme is more fundamental. The choice is a matter of calculational coordinates. Physical predictions agree after parameters are converted and all contributions at the relevant order are included.

## Where the on-shell scheme struggles

The on-shell scheme is cleanest when the theory contains massive stable particles that appear as asymptotic states. Several common situations complicate this picture.

**Unstable particles.** An unstable particle does not have a real-axis pole with an ordinary asymptotic one-particle state. A complex-pole scheme is usually more physical than imposing real on-shell mass and residue conditions naively.

**Massless gauge bosons.** Soft and collinear radiation can obscure simple pole and residue language. Physical observables must be infrared safe or inclusive.

**Confinement.** Quarks and gluons are not asymptotic on-shell particles in QCD. On-shell renormalization of quark or gluon parameters is not the same as defining a directly observed particle mass.

**High-energy logarithms.** If the process energy is far from the physical masses, on-shell parameters can produce large logarithms. Running parameters in a mass-independent scheme may organize perturbation theory better.

## Common pitfalls

**Thinking “on shell” means internal lines are put on shell.** The on-shell scheme fixes renormalized parameters using pole or physical-amplitude data. Loop integrals still integrate over off-shell virtual momenta.

**Using on-shell masses for unstable particles without qualification.** An unstable particle is associated with a complex pole, not an ordinary stable one-particle state. A real mass parameter can be useful, but one must state which convention is being used.

**Forgetting the coupling condition.** Pole and residue conditions fix the two-point function. They do not define $\lambda$, $e$, $g$, or any other interaction strength by themselves.

**Dropping infrared issues.** In theories with massless particles, on-shell amplitudes can be infrared divergent. The scheme can still be used, but physical predictions require inclusive or otherwise infrared-safe observables.

**Comparing on-shell and minimal-subtraction parameters directly.** A pole mass and a running mass are different definitions. They can be related perturbatively, but they are not equal simply because the same letter is used.

## Relations to other pages

- [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/) gives the general framework that the on-shell scheme specializes.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) derives the pole and residue formulas used here.
- [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/) explains the counterterm vertices whose finite pieces implement on-shell conditions.
- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) explains why the residue of a pole controls external-particle normalization.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) connects field-strength conventions to practical scattering amplitudes.
- [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) explains how unstable particles can still appear as approximate resonant intermediate states.

## Research status

The on-shell scheme is textbook-standard for stable particles in perturbation theory. Its subtleties are also well known: gauge dependence of some intermediate definitions, infrared complications in QED and QCD, and unstable-particle mass definitions require care. Modern precision calculations often use hybrid strategies, such as on-shell input observables combined with running parameters, complex-pole masses, or EFT matching schemes.

## Exercises

### Exercise 1: Derive the scalar on-shell counterterms

Starting from

$$
\Sigma_{\rm ren}(p^2)
=\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2,
$$

impose

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

Derive $\delta Z$ and $\delta m^2$.

<details>
<summary><strong>Solution</strong></summary>

The derivative condition gives

$$
0=\operatorname{Re}\Sigma_{\rm loop}'(M^2)-\delta Z,
$$

so

$$
\delta Z=\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

The value condition gives

$$
0=\operatorname{Re}\Sigma_{\rm loop}(M^2)+\delta m^2-M^2\delta Z.
$$

Substituting $\delta Z$ gives

$$
\delta m^2
=-\operatorname{Re}\Sigma_{\rm loop}(M^2)
+M^2\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

</details>

### Exercise 2: Unit residue

Show that if

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0,
$$

then the scalar propagator has unit residue at $p^2=M^2$.

<details>
<summary><strong>Solution</strong></summary>

The denominator is

$$
D(p^2)=p^2-M^2-\Sigma_{\rm ren}(p^2).
$$

Near $M^2$,

$$
D(p^2)
=(p^2-M^2)\left[1-\Sigma_{\rm ren}'(M^2)\right]+\cdots.
$$

The derivative condition sets the real part of the bracket to one. For a stable particle with no imaginary part at the pole,

$$
G_{\rm ren}(p)
\sim
\frac{i}{p^2-M^2+i\epsilon}.
$$

Thus the residue is one.

</details>

### Exercise 3: Why two-point conditions do not fix the coupling

Explain why the two scalar conditions

$$
\Sigma_{\rm ren}(M^2)=0,
\qquad
\Sigma_{\rm ren}'(M^2)=0
$$

do not determine $\delta\lambda$ in $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

The two conditions involve only the two-point function. They fix the counterterms that appear in the quadratic part of the Lagrangian: $\delta m^2$ and $\delta Z$.

The coupling counterterm $\delta\lambda$ appears in the four-point vertex. To fix it, one must impose a condition on a four-point function or a physical scattering amplitude. For example, one may require

$$
\mathcal M_{\rm ren}(s=4M^2,t=0,u=0)=-\lambda_{\rm OS}.
$$

</details>

### Exercise 4: On-shell versus minimal subtraction

Suppose a loop self-energy has the form

$$
\Sigma_{\rm loop}(p^2)=\frac{A+Bp^2}{\epsilon}+F(p^2),
$$

where $F$ is finite. Describe qualitatively how the mass and field-strength counterterms differ in minimal subtraction and in the on-shell scheme.

<details>
<summary><strong>Solution</strong></summary>

In minimal subtraction, the counterterms remove only the pole pieces proportional to $A$ and $B$. Their finite parts are not chosen to make the pole occur at $M^2$ or to make the residue one.

In the on-shell scheme, the counterterms include both pole pieces and finite pieces involving $F(M^2)$ and $F'(M^2)$. These finite pieces enforce

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

Thus the two schemes differ by finite counterterms.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§14–16 and 25–27, for self-energies, pole masses, unstable particles, and schemes.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 15–17 and 25, for renormalized propagators, counterterm determination, and the physical interpretation of renormalization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 18–20, for mass renormalization, counterterms, and infrared-aware perturbative examples.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 10 and 12, for systematic renormalization and the relation between S-matrix elements and renormalized Green functions.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. III.3, for a compact discussion of physical perturbation theory and counterterms.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 9–10, for comparison with minimal subtraction and RG-oriented renormalized QFT.

## Version history

- **2026-06-12:** Initial standardized page.
