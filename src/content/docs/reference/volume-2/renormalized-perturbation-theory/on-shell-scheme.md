---
title: "On-Shell Scheme"
description: "How on-shell renormalization defines masses, residues, and selected couplings directly from physical poles and amplitudes."
sidebar:
  label: "On-Shell Scheme"
  order: 4
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§14–18 and 27; Schwartz chs. 18–19; Weinberg Vol. I ch. 12; Peskin and Schroeder, renormalization chapters."
topics:
  - on-shell scheme
  - pole mass
  - residue renormalization
  - physical renormalization conditions
  - wavefunction renormalization
  - charge renormalization
canonicalTopics:
  - on-shell-renormalization
  - pole-mass
  - field-strength-renormalization
  - physical-renormalization-conditions
researchStatus:
  established:
    - "For stable particles in perturbative theories, on-shell renormalization defines masses and residues by physical pole conditions and gives an especially transparent connection to scattering amplitudes."
  active:
    - "Subtleties remain important for unstable particles, confined colored fields, high-order gauge-theory calculations, infrared singularities, pole-mass renormalons, and precision conversions to short-distance schemes."
---

## Summary

The **on-shell scheme** is a renormalization scheme in which selected renormalized parameters are defined directly by physical pole and amplitude conditions. For a stable scalar particle, the renormalized mass is chosen to be the pole mass, and the renormalized field is normalized so that the propagator has unit residue at the pole:

$$
G_R(p^2)\underset{p^2\to m^2}{\sim}
\frac{i}{p^2-m^2+i\epsilon}+\text{terms regular at }p^2=m^2.
$$

For fermions, the analogous condition is that the exact propagator has a pole at $p^2=m^2$ with the standard Dirac numerator and unit residue. Couplings are fixed by physical amplitudes or form factors at specified kinematic points, such as the Thomson-limit definition of the electric charge in QED.

The on-shell scheme is conceptually appealing because it uses quantities close to what experiments measure: pole positions, residues of asymptotic one-particle states, and low-energy amplitudes. It is also less convenient than minimal subtraction for many high-energy and EFT calculations, because it ties counterterms to physical thresholds and masses rather than to simple pole subtraction.

:::note[The slogan]
In an on-shell scheme, the renormalized parameters are not just convenient coordinates. They are chosen so that selected propagator poles and selected amplitudes already have their physical normalization order by order.
:::

## Prerequisites

You should know [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/), and [Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/). For the local origin of counterterms, review [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) and [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/).

We use the mostly-minus metric and the renormalization conventions fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/). The scalar propagator convention is

$$
\frac{i}{p^2-m^2+i\epsilon}
$$

at tree level.

## Core idea

The on-shell scheme turns the intuitive statement

$$
\text{the particle mass is where the propagator has its pole}
$$

into a renormalization prescription.

Loop corrections change the two-point function. If the renormalized Lagrangian contains a parameter $m$, there is no automatic reason that $m^2$ equals the pole of the corrected propagator. A counterterm scheme must say how $m$ is to be interpreted. In the on-shell scheme, the answer is: choose the mass counterterm so that the corrected pole occurs at $p^2=m^2$.

Loop corrections also change the residue of the pole. If a field is used as an interpolating field for an asymptotic particle, LSZ reduction is sensitive to that residue. In the on-shell scheme, the field-strength counterterm is chosen so that the pole residue is one. Then external-leg residue factors are hidden in the renormalization conditions rather than appearing explicitly in every amplitude.

The core conditions are therefore:

$$
\text{pole position fixed},
\qquad
\text{pole residue fixed},
\qquad
\text{selected coupling fixed by an amplitude}.
$$

This is why the on-shell scheme is often called a **physical scheme**. The phrase is useful, but one should not overread it. Other schemes are not unphysical. They simply use different coordinates, and physical observables agree after conversion.

## Setup and conventions

Consider a scalar theory whose renormalized quadratic Lagrangian and counterterms are written as

$$
\mathcal L_{\text{ren}}
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2+\cdots,
$$

and

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2+\cdots.
$$

Let $\Pi_{\text{loop}}(p^2)$ denote the loop contribution to the scalar self-energy, in the convention where the exact propagator can be written near the pole as

$$
G_R(p^2)=
\frac{i}{p^2-m^2-\Pi_R(p^2)+i\epsilon}.
$$

For the counterterm convention above, write

$$
\Pi_R(p^2)=\Pi_{\text{loop}}(p^2)+\delta Z(p^2-m^2)-\delta m^2.
$$

The scalar on-shell conditions are

$$
\Pi_R(m^2)=0,
\qquad
\left.\frac{d\Pi_R}{dp^2}\right|_{p^2=m^2}=0.
$$

The first equation fixes the pole position. The second fixes the residue. With these conditions,

$$
G_R(p^2)
=\frac{i}{p^2-m^2+i\epsilon}+\text{regular terms}
$$

near $p^2=m^2$.

For amplitudes, the same philosophy applies: impose a condition at a physical or near-physical kinematic point. For example, a scalar quartic coupling could be defined by requiring a specified $2\to2$ amplitude at a specified point to equal $-\lambda_{\text{os}}$, up to the sign and $i$ conventions of the amplitude normalization. In QED, the on-shell electric charge is commonly tied to the low-energy electromagnetic interaction, equivalently to the Thomson limit or the long-distance Coulomb potential.

## Scalar pole and residue conditions

The pole condition is easy to state but worth unpacking. The corrected denominator is

$$
D_R^{-1}(p^2)=p^2-m^2-\Pi_R(p^2).
$$

A pole at $p^2=m^2$ requires

$$
D_R^{-1}(m^2)=0.
$$

Since $D_R^{-1}(m^2)=-\Pi_R(m^2)$, this is just $\Pi_R(m^2)=0$.

The residue condition follows from expanding near the pole:

$$
D_R^{-1}(p^2)
=(p^2-m^2)
\left[1-\Pi_R'(m^2)\right]
+O\left((p^2-m^2)^2\right).
$$

Thus

$$
G_R(p^2)
\sim
\frac{i}{(p^2-m^2)\left[1-\Pi_R'(m^2)\right]+i\epsilon}.
$$

The pole residue is

$$
Z_{\text{pole}}=\frac{1}{1-\Pi_R'(m^2)}.
$$

The on-shell residue condition sets $Z_{\text{pole}}=1$, equivalently

$$
\Pi_R'(m^2)=0.
$$

At one loop, using

$$
\Pi_R(p^2)=\Pi_{\text{loop}}(p^2)+\delta Z(p^2-m^2)-\delta m^2,
$$

the on-shell conditions give

$$
\delta m^2=\Pi_{\text{loop}}(m^2),
\qquad
\delta Z=-\Pi_{\text{loop}}'(m^2).
$$

This compact formula is the workhorse of on-shell mass and field-strength renormalization.

:::tip[What is being normalized?]
The field $\phi$ itself is not an observable. The residue condition normalizes how strongly $\phi$ creates the one-particle state used by LSZ reduction. This is why the field-strength counterterm matters even though local field normalizations are convention-dependent.
:::

## Fermion pole conditions

For a Dirac fermion, write the exact renormalized propagator as

$$
S_R(p)=\frac{i}{p\!\!\!/-m-\Sigma_R(p)+i\epsilon}.
$$

Lorentz invariance allows the self-energy to be decomposed as

$$
\Sigma_R(p)=p\!\!\!/\,\Sigma_V(p^2)+m\Sigma_S(p^2),
$$

up to convention-dependent signs and chiral generalizations. The on-shell condition requires that the inverse propagator vanish when acting on an on-shell spinor:

$$
\left[p\!\!\!/-m-\Sigma_R(p)\right]u(p)=0
\qquad\text{at }p^2=m^2.
$$

The residue condition requires the propagator to approach

$$
S_R(p)
\underset{p^2\to m^2}{\sim}
\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}
+\text{regular terms}.
$$

In practice, one expresses the fermion counterterms in terms of mass and field-strength renormalization constants and solves the pole-position and residue equations order by order.

For chiral gauge theories or fermion mixing, the bookkeeping is more elaborate. Mass matrices, flavor rotations, left- and right-handed field renormalizations, gauge fixing, and unstable-particle effects all matter. The basic physical idea, however, remains the same: the pole structure of the exact two-point function defines the mass and residue when an isolated stable one-particle state exists.

## Coupling conditions

Masses and residues are two-point data. A coupling condition fixes an interaction strength. In an on-shell scheme this is done with a physical amplitude or form factor.

A schematic scalar example is

$$
\mathcal M_R(2\to2)\big|_{\text{chosen physical point}}
=-\lambda_{\text{os}}.
$$

The exact kinematic point must be stated. Different choices give different physical schemes. If the chosen point is near a threshold or singularity, the scheme may be inconvenient or ill-conditioned.

In QED, a standard on-shell charge definition uses the low-momentum electromagnetic interaction. Schematic vertex normalization is

$$
\Gamma_R^\mu(p,p)\big|_{p^2=m^2,q=0}
=\gamma^\mu,
$$

with the electric charge carried by the overall coupling. Equivalently, one may define $\alpha$ from the long-distance Coulomb potential or from the Thomson limit. Ward identities make the relation between vertex, electron field, and charge renormalization especially simple in QED.

The price of using physical coupling definitions is that they may be tied to specific masses and thresholds. That is excellent for low-energy precision QED, but less ideal for high-energy processes where large logarithms of the form

$$
\log\frac{Q^2}{m^2}
$$

can appear. In such cases, short-distance schemes such as $\overline{\mathrm{MS}}$ are often better computational coordinates.

## On-shell conditions and LSZ

LSZ reduction relates scattering amplitudes to residues of time-ordered correlation functions. If a scalar two-point function has the form

$$
G(p^2)
\sim
\frac{iZ_{\text{pole}}}{p^2-m_{\text{phys}}^2+i\epsilon},
$$

then each external scalar leg contributes a factor $Z_{\text{pole}}^{-1/2}$ in the extraction of the invariant amplitude, assuming the field is used as the interpolating field for that particle.

The on-shell scheme chooses the renormalized field so that

$$
Z_{\text{pole}}=1.
$$

This does not remove LSZ. It bakes the LSZ residue normalization into the definition of the renormalized field.

This is why on-shell calculations often look physically direct. External propagator residues do not clutter the final formula, because the counterterms were chosen to make the pole residues canonical.

## Advantages

The on-shell scheme has several strengths.

First, it gives immediate physical interpretation to selected parameters. A mass parameter $m$ is the physical pole mass of a stable particle. This is a gift to intuition.

Second, it is well adapted to processes with stable asymptotic particles and low-energy normalization conditions. Classic QED calculations often look natural in on-shell language.

Third, it keeps threshold physics visible. A physical scheme knows about particle masses and physical branch points. That can be useful when the relevant physics is near a threshold.

Fourth, it is a good diagnostic for understanding what counterterms do. The mass counterterm moves the pole. The field-strength counterterm adjusts the residue. The coupling counterterm normalizes a physical interaction. The bookkeeping has a clean job description.

## Limitations

The same features that make the on-shell scheme intuitive also make it awkward in many modern calculations.

**Massless particles bring infrared subtleties.** If the particle is massless and interacts with massless quanta, the idea of an isolated one-particle pole can be complicated by infrared divergences, soft radiation, and inclusive-state issues. QED and QCD both force care here.

**Unstable particles do not have ordinary asymptotic states.** An unstable particle produces a resonance pole at complex $p^2$, not a stable real-axis pole with an ordinary one-particle external state. Precision electroweak theory therefore often uses complex-pole schemes or carefully defined mass schemes rather than a naive real on-shell prescription.

**Confined fields do not define physical poles.** Quark and gluon propagators are useful gauge-fixed objects in perturbation theory, but isolated quarks and gluons are not asymptotic physical particles in QCD. An on-shell quark mass can be used perturbatively, but it is not a clean long-distance physical observable.

**Pole masses can be poor short-distance parameters.** In QCD, heavy-quark pole masses suffer from an intrinsic long-distance ambiguity of order $\Lambda_{\mathrm{QCD}}$. Short-distance masses such as $\overline{\mathrm{MS}}$, kinetic, 1S, or potential-subtracted masses are often better for precision.

**Large logarithms may be left unresummed.** If a process has $Q\gg m$, on-shell parameters defined at $p^2=m^2$ can produce large logarithms. RG-friendly schemes let one choose $\mu\sim Q$ and resum such logarithms.

The on-shell scheme is therefore not the universally best scheme. It is the right scheme when physical pole normalization is the cleanest way to organize the question.

## Relation to minimal subtraction

Minimal subtraction defines parameters by removing poles in dimensional regularization. On-shell renormalization defines parameters by physical conditions.

For a mass, this means:

$$
m_{\text{os}}^2
=m_{\overline{\mathrm{MS}}}^2(\mu)
+\Delta m^2(\mu),
$$

where $\Delta m^2$ is a finite, scheme-dependent conversion computed perturbatively when both definitions are valid.

For a coupling,

$$
g_{\text{os}}
=g_{\overline{\mathrm{MS}}}(\mu)
+\Delta g(\mu).
$$

The conversion contains logarithms and constants. A physical observable may be written in either scheme:

$$
\mathcal O
=\mathcal O_{\text{os}}(m_{\text{os}},g_{\text{os}})
=\mathcal O_{\overline{\mathrm{MS}}}(m_{\overline{\mathrm{MS}}}(\mu),g_{\overline{\mathrm{MS}}}(\mu),\mu)
$$

up to the order being computed. At finite perturbative order, residual scheme dependence remains as an estimate of missing higher-order terms.

## Worked example: scalar two-point counterterms

Suppose the loop self-energy has the Taylor expansion near $p^2=m^2$

$$
\Pi_{\text{loop}}(p^2)
=A+B(p^2-m^2)+O\left((p^2-m^2)^2\right),
$$

where $A$ and $B$ may contain regulator-dependent pieces. With

$$
\Pi_R(p^2)=\Pi_{\text{loop}}(p^2)+\delta Z(p^2-m^2)-\delta m^2,
$$

the on-shell conditions give

$$
\delta m^2=A,
\qquad
\delta Z=-B.
$$

Then

$$
\Pi_R(p^2)=O\left((p^2-m^2)^2\right).
$$

The corrected inverse propagator is

$$
D_R^{-1}(p^2)=p^2-m^2+O\left((p^2-m^2)^2\right),
$$

so the pole location and residue are exactly the tree-level-looking ones, by construction.

This example also shows what on-shell counterterms do not do. They do not erase the finite nonlocal dependence of the self-energy away from the pole. Branch cuts, thresholds, logarithms, and imaginary parts remain. Those are physical loop effects, not counterterm mistakes.

## Common pitfalls

**Thinking that on-shell means no loops.** The on-shell scheme does not remove loop effects. It chooses counterterms so that selected pole and amplitude data keep simple definitions. Loop corrections still affect scattering, form factors, threshold behavior, and running when written in other schemes.

**Confusing the Lagrangian mass with the pole mass in every scheme.** In an on-shell scheme these are identified by convention. In $\overline{\mathrm{MS}}$ they are not.

**Using on-shell conditions where no stable particle exists.** A resonance is not an asymptotic state. A confined quark is not an isolated physical particle. A massless charged particle in a theory with long-range radiation requires infrared care.

**Forgetting gauge dependence.** Physical pole positions for stable particles are gauge independent, but off-shell Green functions and many intermediate definitions are not. Gauge-dependent on-shell-looking conditions can be misleading if imposed on unphysical fields.

**Assuming physical schemes are always numerically better.** A physical definition can be intuitive and still produce large logarithms. For high-energy or multi-scale problems, $\overline{\mathrm{MS}}$ or EFT threshold schemes may be cleaner.

## Relations to other pages

[Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/) explains the opposite extreme: subtract only pole parts and let parameters run with $\mu$.

[Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/) develops the residue and field-normalization story in more detail.

[Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/) compares pole masses, running masses, physical couplings, and short-distance couplings.

[Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/) explains how these conditions enter LSZ-normalized scattering amplitudes.

[Matching](/renormalization-rg-eft/effective-field-theory/matching/) and [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) explain why physical and short-distance schemes must often be converted at heavy-particle thresholds.

## Research status

The basic on-shell scheme for stable particles is standard. The important modern issues are not whether the scheme exists, but where it is the right tool.

In precision electroweak theory, unstable particles require careful mass and width definitions, often using complex pole masses. In QCD, pole masses are conceptually limited by long-distance sensitivity, so short-distance masses are preferred for precision heavy-quark physics. In collider calculations, on-shell input observables are often combined with $\overline{\mathrm{MS}}$ running couplings, EFT Wilson coefficients, and resummation schemes. The practical art is choosing a scheme that keeps physical interpretation, perturbative convergence, gauge consistency, and scale separation under control.

## Exercises

### Exercise 1: Derive the scalar on-shell counterterms

Assume

$$
\Pi_R(p^2)=\Pi_{\text{loop}}(p^2)+\delta Z(p^2-m^2)-\delta m^2.
$$

Impose

$$
\Pi_R(m^2)=0,
\qquad
\Pi_R'(m^2)=0.
$$

Solve for $\delta m^2$ and $\delta Z$.

<details><summary><strong>Solution</strong></summary>

The first condition gives

$$
0=\Pi_R(m^2)
=\Pi_{\text{loop}}(m^2)-\delta m^2,
$$

so

$$
\delta m^2=\Pi_{\text{loop}}(m^2).
$$

Differentiating gives

$$
\Pi_R'(p^2)=\Pi_{\text{loop}}'(p^2)+\delta Z.
$$

Therefore

$$
0=\Pi_R'(m^2)=\Pi_{\text{loop}}'(m^2)+\delta Z,
$$

so

$$
\delta Z=-\Pi_{\text{loop}}'(m^2).
$$

</details>

### Exercise 2: Residue before field-strength renormalization

Suppose a scalar propagator near its pole has denominator

$$
D^{-1}(p^2)=p^2-m^2-\Pi(p^2),
$$

with $\Pi(m^2)=0$ but $\Pi'(m^2)\ne0$. Show that the pole residue is

$$
Z_{\text{pole}}=\frac{1}{1-\Pi'(m^2)}.
$$

<details><summary><strong>Solution</strong></summary>

Expand the denominator near $p^2=m^2$:

$$
D^{-1}(p^2)
=(p^2-m^2)-\Pi'(m^2)(p^2-m^2)+O\left((p^2-m^2)^2\right).
$$

Thus

$$
D^{-1}(p^2)
=(p^2-m^2)\left[1-\Pi'(m^2)\right]
+O\left((p^2-m^2)^2\right).
$$

Therefore

$$
G(p^2)=\frac{i}{D^{-1}(p^2)+i\epsilon}
\sim
\frac{i}{(p^2-m^2)\left[1-\Pi'(m^2)\right]+i\epsilon}.
$$

The coefficient multiplying $i/(p^2-m^2+i\epsilon)$ is

$$
Z_{\text{pole}}=\frac{1}{1-\Pi'(m^2)}.
$$

</details>

### Exercise 3: Why large logarithms disfavor a low-energy on-shell coupling

Suppose a high-energy amplitude has the schematic perturbative form

$$
\mathcal M(Q)=g_{\text{os}}^2
\left[1+c g_{\text{os}}^2\log\frac{Q^2}{m^2}+O(g_{\text{os}}^4)\right],
\qquad Q\gg m.
$$

Explain why a running coupling defined at $\mu\sim Q$ may be a better expansion parameter.

<details><summary><strong>Solution</strong></summary>

The logarithm $\log(Q^2/m^2)$ can be large when $Q\gg m$. Then the nominal one-loop correction

$$
c g_{\text{os}}^2\log\frac{Q^2}{m^2}
$$

may be comparable to one even when $g_{\text{os}}^2$ itself is small. This spoils the apparent convergence of fixed-order perturbation theory in the low-energy on-shell coupling.

A running coupling $g(\mu)$ defined in a short-distance scheme can be evaluated at $\mu\sim Q$. The large logarithms are then reorganized into RG evolution between $m$ and $Q$, leaving the fixed-order coefficients with smaller logarithms. This is not a change of physics; it is a better choice of perturbative coordinates for a multi-scale problem.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the renormalization lectures on counterterms, propagator normalization, and physical renormalization.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on loop corrections, other renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 18–19 on mass renormalization and renormalized perturbation theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, for a general and scheme-aware treatment of renormalization.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, for standard on-shell counterterm examples in scalar theory and QED.
- A. Sirlin, "Radiative corrections in the $SU(2)_L\times U(1)$ theory: A simple renormalization framework," for classic electroweak on-shell renormalization.

## Version history

- 2026-06-17: First polished draft. Defined scalar and fermion on-shell conditions, pole and residue normalization, coupling conditions, LSZ relation, advantages, limitations, and scheme-conversion context.
