---
title: "Physical Parameters"
description: "How masses, couplings, charges, widths, matrix elements, and EFT coefficients are defined from observables rather than from bare symbols in a Lagrangian."
sidebar:
  label: "Physical Parameters"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§13–15 and 27–29; Coleman, Renormalization and Symmetry and Dilatations; Weinberg Vol. I chs. 10–12 and Vol. II ch. 18; Schwartz chs. 18–23; Burgess 2020 chs. 1–3."
topics:
  - physical parameters
  - renormalization conditions
  - pole mass
  - running couplings
  - scheme dependence
  - EFT Wilson coefficients
canonicalTopics:
  - physical-parameter
  - pole-mass
  - renormalization-condition
  - running-coupling
  - scheme-dependence
  - wilson-coefficient
researchStatus:
  established:
    - "Physical parameters are defined by observables or precise operational prescriptions; bare and renormalized Lagrangian parameters are coordinates used to compute them."
  active:
    - "Subtleties remain important for unstable particles, gauge-dependent off-shell quantities, confinement, composite operators, lattice-to-continuum matching, and EFT parameter inference."
---

## Summary

A physical parameter is a number extracted from a well-defined observable or from a precise theoretical definition tied to observables. A symbol in a Lagrangian becomes physical only after one states how it is measured, matched, or otherwise fixed.

The distinction is simple but load-bearing:

| Quantity | Example | Physical by itself? | Why |
|---|---|---|---|
| bare parameter | $m_0^2$, $e_0$, $\lambda_0$ | usually no | depends on regulator and cutoff convention |
| renormalized parameter | $m^2(\mu)$, $e(\mu)$, $\lambda_{\overline{\mathrm{MS}}}(\mu)$ | usually no | depends on scheme and scale |
| physical parameter | pole mass, decay width, scattering length, threshold amplitude | yes, if well defined | extracted from observables or invariant singularities |
| EFT coefficient | $C_i(\mu)$ | not by itself | depends on basis, scheme, and matching convention |

The safest slogan is

$$
\text{parameters in the Lagrangian are coordinates; observables are the target.}
$$

A renormalization condition is a rule for choosing coordinates so that selected observables take specified values. Once enough physical inputs are used to fix the coordinates, the theory predicts other observables.

:::note[The recurring trap]
It is common to say “the electron mass,” “the charge,” or “the coupling” as if each phrase named a single convention-independent number. In precision QFT, those phrases are shorthand. One must specify pole mass or running mass, low-energy charge or short-distance charge, threshold coupling or $\overline{\mathrm{MS}}$ coupling, stable particle or resonance, elementary field or composite operator.
:::

## Prerequisites

You should have read [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/). This page assumes the distinction among bare parameters, renormalized parameters, and observables.

You should also keep the volume [Conventions and Notation](/renormalization-rg-eft/conventions/) nearby, especially the distinction between the cutoff $\Lambda$, the renormalization scale $\mu$, and the physical scale $Q$.

## Core idea

A QFT is not fully specified by writing a formal expression such as

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The symbols $m^2$ and $\lambda$ are not automatically measured numbers. In a quantum theory they depend on how the theory is regulated and how the parameters are defined. To make contact with physics, one must say which observables are used as inputs.

For example, one might choose:

$$
\text{pole location of a two-point function},
\qquad
\text{residue of a pole},
\qquad
\text{four-point amplitude at a fixed kinematic point},
$$

or one might choose a mass-independent scheme such as $\overline{\mathrm{MS}}$, define $m(\mu)$ and $\lambda(\mu)$ there, and determine their numerical values by fitting measured observables.

The first choice makes contact with physical quantities early. The second choice often makes high-order calculations and multi-scale running cleaner. Neither choice changes the physics when used consistently.

The conceptual map is

$$
\text{renormalized coordinates}
\quad + \quad
\text{renormalization conditions}
\quad \longrightarrow \quad
\text{physical predictions}.
$$

Coordinates are useful. Confusing them with the geometry is how one gets lost.

## Setup and conventions

We use mostly-minus Lorentzian conventions. For a scalar two-point function, write the renormalized one-particle-irreducible two-point function schematically as

$$
\Gamma_R^{(2)}(p^2)
=p^2-m^2(\mu)-\Pi_R(p^2;m(\mu),g(\mu),\mu),
$$

where $\Pi_R$ is the renormalized self-energy in a chosen scheme. The full connected propagator is schematically

$$
G_R(p)=\frac{i}{\Gamma_R^{(2)}(p^2)+i\epsilon}.
$$

The precise sign convention for $\Pi_R$ varies across books. The invariant statement is that physical masses are associated with singularities of the propagator or of the $S$-matrix, not with arbitrary intermediate symbols.

For couplings, we use $g(\mu)$ for a running renormalized coupling and $g_{\text{phys}}$ only when an operational definition has been stated. The expression “the physical coupling” is otherwise too vague.

## Parameters as coordinates on theory space

Think of theory space as the set of QFTs compatible with a chosen field content, locality, and symmetries. A Lagrangian is a coordinate chart on that space:

$$
S=\sum_i g_i\int d^d x\,\mathcal O_i(x).
$$

Changing renormalization scheme is a change of coordinates:

$$
g^i\longrightarrow g^{\prime i}(g).
$$

Changing operator basis in EFT is also a change of coordinates:

$$
\mathcal O_i\longrightarrow R_i{}^j\mathcal O_j,
\qquad
C_i\longrightarrow (R^{-1})_i{}^jC_j,
$$

possibly with additional shifts from equations of motion and field redefinitions.

A physical observable is a function on theory space. In coordinates it is written as

$$
\mathcal O_{\text{phys}}
=F(g^i(\mu),Q/\mu),
$$

where $Q$ denotes physical kinematic scales. The function $F$ changes appearance when coordinates change, but its value does not.

This is why it is not meaningful to ask whether $g(\mu)$ alone is observable. The observable is obtained after inserting $g(\mu)$ into a calculation with the stated scheme, scale, and observable definition.

## Pole masses for stable particles

For a stable one-particle state, a physical mass can be defined by the pole of the exact two-point function. In the scalar notation above, the pole mass $m_{\text{pole}}$ satisfies

$$
\Gamma_R^{(2)}(m_{\text{pole}}^2)=0.
$$

Equivalently,

$$
m_{\text{pole}}^2-m^2(\mu)-\Pi_R(m_{\text{pole}}^2)=0.
$$

This equation relates the scheme-dependent running mass $m(\mu)$ to the physical pole position. The pole position is invariant; the split between $m^2(\mu)$ and $\Pi_R$ is not.

Near a simple pole,

$$
G_R(p)
\sim
\frac{iZ_{\text{pole}}}{p^2-m_{\text{pole}}^2+i\epsilon}
+\text{less singular terms},
$$

where

$$
Z_{\text{pole}}^{-1}
=\left.\frac{d\Gamma_R^{(2)}(p^2)}{dp^2}\right|_{p^2=m_{\text{pole}}^2}.
$$

The pole location is physical for a stable isolated particle. The residue can be physical in the sense that it enters LSZ normalization for the chosen interpolating field, but field normalizations themselves are not observables. A field redefinition can change the field variable without changing the $S$-matrix.

:::tip[Mass means definition]
When someone says “the mass parameter,” ask which one: bare mass, running mass, pole mass, screening mass, curvature of an effective potential, lattice mass gap, or resonance pole. In many simple examples they are close. In precision work they are different objects.
:::

## Unstable particles and resonance parameters

Unstable particles do not correspond to normalizable asymptotic one-particle states. Their propagators have no real-axis pole with the stable-particle interpretation above. Instead, a resonance is associated with a pole after analytic continuation to an unphysical sheet:

$$
s_*=M_*^2-iM_*\Gamma_*+	ext{higher-width convention terms}.
$$

The complex pole position is a physical feature of the analytic $S$-matrix when the resonance is well isolated. By contrast, Breit–Wigner masses and widths extracted from a line shape can depend on the parametrization used to fit the data.

This is not pedantry. In gauge theories, naive off-shell self-energies and real-axis mass parameters can be gauge dependent. Pole definitions are much safer because they are tied to physical singularities.

## Couplings from amplitudes

A coupling can be defined from a scattering process. For a scalar theory with interaction convention

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4,
$$

one may define a momentum-subtraction coupling by imposing a condition on the renormalized one-particle-irreducible four-point function at a chosen Euclidean symmetric point:

$$
\Gamma_R^{(4)}(p_1,p_2,p_3,p_4)\big|_{\text{symmetric point}}
=-\lambda_{\text{MOM}}(\mu).
$$

The symmetric point is part of the definition. A different point gives a different coupling. A threshold scattering amplitude gives another possible definition. A minimal-subtraction coupling gives yet another.

The corresponding physical prediction is not the isolated symbol $\lambda_{\text{MOM}}$. It is the full amplitude,

$$
\mathcal M(s,t,u)
=\mathcal M(s,t,u;\lambda_{\text{MOM}}(\mu),m(\mu),\mu),
$$

after the coupling has been fixed by the chosen renormalization condition.

This is the right way to understand running couplings. A running coupling is a convenient way of organizing how amplitudes depend on scale. It is not, by itself, an observable that floats through the vacuum wearing a name tag.

## Charges and low-energy definitions

Some parameters have especially natural physical definitions because they are tied to long-distance forces or conserved currents. In QED, the electric charge may be defined from the long-distance Coulomb potential or from a low-energy scattering limit. Once this definition is chosen, radiative corrections determine how short-distance processes are expressed in terms of that input.

One may also define an effective charge at momentum transfer $q^2$ by reorganizing the photon propagator and vacuum polarization:

$$
e_{\text{eff}}^2(q^2)
=\frac{e^2}{1-\Pi_R(q^2)}
$$

schematically. This is useful, but it is a process- and convention-aware construction. In non-Abelian gauge theory, the phrase “the running coupling” is even more scheme dependent because the coupling is not defined by a directly measurable long-range Coulomb force in the confining regime.

The rule is:

$$
\text{a charge is physical when its normalization is fixed by a physical current or a precise observable.}
$$

Ward identities can protect some normalizations. Composite-operator normalizations without such protection require renormalization conditions just like couplings do.

## Renormalization conditions as input choices

A theory with $N$ independent parameters needs $N$ independent input conditions. These may be experimental measurements, lattice outputs, matching conditions to a more microscopic theory, or exact symmetry constraints.

Schematically, suppose the renormalized parameters are $g^1(\mu),\ldots,g^N(\mu)$ and the chosen input observables are $O_1,\ldots,O_N$. The renormalization conditions are

$$
O_a^{\text{theory}}(g^i(\mu),\mu)=O_a^{\text{input}}.
$$

Solving these equations fixes the coordinates $g^i(\mu)$. Then any other observable $O_{N+1}$ is predicted:

$$
O_{N+1}^{\text{prediction}}
=O_{N+1}^{\text{theory}}(g^i(\mu),\mu).
$$

The coordinate values depend on the scheme. The predicted value, computed exactly, does not.

In practice calculations are truncated, so a prediction may retain residual $\mu$ dependence. This residual dependence is not physical; it estimates the size of omitted higher-order terms only when used with care.

## Scale independence of observables

Let $F$ be a dimensionless physical observable depending on a physical scale $Q$, running couplings $g^i(\mu)$, running masses $m_a(\mu)$, and the arbitrary scale $\mu$. Exact physics satisfies

$$
\mu\frac{d}{d\mu}F=0.
$$

Expanded out, this becomes an RG equation of the form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
-\gamma_{m_a}m_a\frac{\partial}{\partial m_a}
\right)F=0,
$$

with signs depending on the mass anomalous-dimension convention. The essential point is not the sign in this schematic formula. It is that explicit $\mu$ dependence in the loop calculation cancels implicit $\mu$ dependence in the running parameters.

At finite order, the cancellation is incomplete:

$$
\mu\frac{d}{d\mu}F_{\text{truncated}}
=O(\text{next order}).
$$

This is why scale variation is a diagnostic of perturbative uncertainty, not a new physical effect.

## Physical schemes and mass-independent schemes

Different schemes are useful for different jobs.

| Scheme type | Typical condition | Strength | Weakness |
|---|---|---|---|
| on-shell | pole masses and residues fixed directly | close to measurable quantities for stable particles | awkward for massless particles, unstable particles, and multi-scale problems |
| momentum subtraction | Green functions fixed at chosen momenta | intuitive and process-like | depends on gauge and off-shell choices unless defined carefully |
| MS or $\overline{\mathrm{MS}}$ | subtract poles, or $1/\bar\epsilon$ combinations | efficient, symmetry-friendly, mass-independent | parameters are not directly measured |
| lattice bare scheme | couplings at lattice spacing $a$ | nonperturbative definition | continuum interpretation requires tuning and matching |
| EFT matching scheme | coefficients fixed at a threshold | separates scales cleanly | coefficients depend on basis and scheme |

There is no universally best scheme. A good scheme makes the calculation transparent, stable, and easy to compare with data.

## EFT coefficients are not observables by themselves

In an EFT below a heavy scale $M$, write

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\sum_i\frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i.
$$

The Wilson coefficients $C_i(\mu)$ are indispensable, but they are not directly observable in isolation. They depend on:

- the operator basis;
- field redefinitions;
- equations-of-motion choices;
- the renormalization scheme;
- the matching scale;
- the convention used to normalize operators.

The physical content lies in amplitudes, rates, energy shifts, correlation functions, and other observables computed from the whole EFT.

For example, two EFT bases related by a field redefinition may have different coefficients but identical $S$-matrix elements. Similarly, two matching scales may give different $C_i(\mu)$ but the same low-energy prediction after running is included.

## What is not physical

Several quantities are useful but not physical by themselves.

**Off-shell Green functions.** They depend on field choices, gauge choices, and renormalization conventions. They are excellent computational tools, but an off-shell Green function is usually not an observable.

**Field normalization constants.** The constant $Z_\phi$ depends on the field variable and the scheme. Pole residues for stable particles enter physical amplitudes through LSZ, but the normalization of an arbitrary interpolating field is not itself a measured number.

**Gauge-fixing parameters.** The gauge parameter $\xi$ in a covariant gauge can appear in intermediate propagators and self-energies. Proper observables do not depend on it.

**Running couplings without a definition.** The phrase $g(Q)$ is useful shorthand only after a scheme and a relation between $Q$ and an observable have been stated.

**Wilson coefficients without a basis.** An EFT coefficient has meaning only together with its operator basis and renormalization convention.

## Example: pole mass versus running mass

Suppose a one-loop calculation gives

$$
\Pi_R(p^2)=\frac{g^2}{16\pi^2}
\left[A p^2\log\frac{-p^2}{\mu^2}+B m^2\log\frac{m^2}{\mu^2}+\text{finite scheme terms}\right]
$$

schematically. The pole condition is

$$
m_{\text{pole}}^2-m^2(\mu)-\Pi_R(m_{\text{pole}}^2)=0.
$$

Solving perturbatively gives

$$
m_{\text{pole}}^2
=m^2(\mu)+\Pi_R(m^2(\mu))+O(g^4).
$$

The right side contains explicit logarithms of $\mu$. The running of $m^2(\mu)$ cancels this dependence to the order computed. Therefore the pole mass is not running, even though the mass parameter in the Lagrangian is.

This is one of the cleanest examples of the theme:

$$
\text{running parameter} + \text{explicit loop dependence}
=\text{scale-independent physical quantity}.
$$

## Example: a scattering length

Low-energy nonrelativistic scattering can be characterized by a scattering length $a$. For short-range interactions, the leading amplitude has the schematic form

$$
\mathcal A(k)
=\frac{4\pi}{M}\frac{1}{-1/a-ik+O(k^2)}.
$$

Here $a$ is physical: it is extracted from the low-energy behavior of the amplitude. An EFT may reproduce this amplitude using a contact interaction with coefficient $C_0(\mu)$. The coefficient $C_0(\mu)$ runs and depends on the subtraction convention. The scattering length does not.

Thus even in a very simple EFT, the measured low-energy parameter and the Lagrangian coefficient are not the same object.

## Common pitfalls

**Calling every Lagrangian coefficient physical.** A coefficient becomes physically meaningful only after its definition is tied to observables, symmetries, or a specified scheme.

**Thinking pole masses are always the best masses.** Pole masses are natural for stable particles. They can be problematic for confined particles, unstable particles, and quantities sensitive to long-distance dynamics.

**Treating running as literal time evolution.** RG running is not a particle changing its charge as it flies. It is the change of a parameter with the scale at which the theory is described or probed.

**Comparing couplings across schemes.** A number quoted as $g(\mu)=0.7$ is incomplete without the scheme, scale, normalization, and sometimes gauge or operator basis.

**Mistaking fitted EFT coefficients for direct observables.** EFT coefficients are coordinates. Physical information is in scheme-consistent predictions and correlations among observables.

## Relations to other pages

[Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/) explains the coordinate split between bare and renormalized quantities. This page explains how those coordinates are tied to physical input data.

[Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/) explains why physical predictions do not depend on the arbitrary regulator once local counterterms and renormalization conditions are used consistently.

Later pages on renormalization conditions, minimal subtraction, Callan–Symanzik equations, matching, running, and decoupling will make these ideas computational.

## Research status

The basic distinction between bare, renormalized, and physical parameters is settled. It is part of the standard grammar of modern QFT.

The subtle part is not the principle but the implementation. Precision gauge theory, unstable-particle physics, lattice matching, nonperturbative mass gaps, quark masses, confinement, EFT global fits, and composite-operator matrix elements require careful definitions. Many modern disagreements about “the value of a parameter” are really disagreements about definitions, schemes, or which observable is being used as input.

## Exercises

### Exercise 1: Pole mass at first order

Let

$$
\Gamma_R^{(2)}(p^2)=p^2-m^2-\Pi_R(p^2),
$$

where $\Pi_R=O(g^2)$. Show that the pole mass satisfies

$$
m_{\text{pole}}^2=m^2+\Pi_R(m^2)+O(g^4).
$$

<details><summary><strong>Solution</strong></summary>

The pole condition is

$$
0=\Gamma_R^{(2)}(m_{\text{pole}}^2)
=m_{\text{pole}}^2-m^2-\Pi_R(m_{\text{pole}}^2).
$$

Write

$$
m_{\text{pole}}^2=m^2+\delta m^2,
$$

where $\delta m^2=O(g^2)$. Then

$$
0=\delta m^2-\Pi_R(m^2+\delta m^2).
$$

Expanding the self-energy,

$$
\Pi_R(m^2+\delta m^2)
=\Pi_R(m^2)+\delta m^2\Pi_R'(m^2)+\cdots.
$$

Since $\Pi_R'(m^2)=O(g^2)$ and $\delta m^2=O(g^2)$, the product is $O(g^4)$. Therefore

$$
\delta m^2=\Pi_R(m^2)+O(g^4),
$$

which gives the result.

</details>

### Exercise 2: Running parameter, fixed observable

Suppose a dimensionless observable has the one-loop form

$$
F(Q)=g(\mu)+b g^2(\mu)\log\frac{Q}{\mu}+O(g^3).
$$

Find the one-loop beta function required by $\mu dF/d\mu=O(g^3)$.

<details><summary><strong>Solution</strong></summary>

Differentiate to order $g^2$:

$$
\mu\frac{dF}{d\mu}
=\beta_g-b g^2+O(g^3).
$$

Terms from differentiating $g^2$ inside the logarithmic term are $O(g^3)$ and can be ignored at this order. Setting the result to zero gives

$$
\beta_g=b g^2+O(g^3).
$$

The running of $g(\mu)$ cancels the explicit $\mu$ dependence in the logarithm.

</details>

### Exercise 3: Field redefinitions and observables

Consider a scalar field redefinition

$$
\phi\longrightarrow \phi'=\phi+a\phi^3/M^2,
$$

where $a$ is dimensionless and $M$ is a heavy scale. Explain why the coefficient of a dimension-six operator may change while physical scattering amplitudes remain unchanged.

<details><summary><strong>Solution</strong></summary>

A field redefinition changes the coordinates used to describe field configurations. Substituting $\phi=\phi'-a\phi'^3/M^2+\cdots$ into the action reshuffles terms among operators. In particular, it can move contributions between derivative operators, potential operators, and operators proportional to the lowest-order equations of motion.

The path integral and the $S$-matrix are invariant under suitable local, invertible field redefinitions, up to Jacobian effects that are themselves local and can be absorbed into coefficients. Therefore individual EFT coefficients can change while physical amplitudes remain the same. This is why Wilson coefficients must be quoted with an operator basis and convention.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the sections on the exact propagator, renormalization schemes, the renormalization group, and effective field theory.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Renormalization and Symmetry."
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 18–23.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the discussions of renormalized parameters, RG equations, and critical observables.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 1–3 on effective actions, matching, and power counting.

## Version history

- 2026-06-16: First polished draft. Introduced physical parameter definitions, pole masses, couplings from amplitudes, renormalization conditions, scheme dependence, unstable-particle caveats, and EFT coefficient interpretation.
