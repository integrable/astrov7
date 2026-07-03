---
title: "Integrating Out Heavy Fields"
description: "The path-integral, classical, and one-loop meaning of removing heavy fields and replacing their effects by local EFT operators."
sidebar:
  label: "Integrating Out Heavy Fields"
  order: 4
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I and II, effective actions and RG methods; Schwartz 2014, effective actions and EFT examples; Burgess 2020, effective actions, Wilson actions, and matching; Coleman 1985, functional methods and renormalization."
topics:
  - integrating out heavy fields
  - effective action
  - Wilson coefficients
  - functional determinants
  - local operator expansion
canonicalTopics:
  - integrating-out-heavy-fields
  - low-energy-effective-action
  - functional-matching
researchStatus:
  established:
    - "Integrating out heavy fields is the standard operation that defines a low-energy effective action whose local expansion is fixed by matching."
  active:
    - "Efficient gauge-covariant functional matching, multi-loop heavy-field integration, EFTs with unstable particles, and nonperturbative matching remain active technical areas."
---

## Summary

To **integrate out a heavy field** is to remove it from the list of explicit low-energy degrees of freedom and replace its effects by interactions among the remaining light fields. In path-integral language, if $H$ is heavy and $\phi$ is light, the low-energy effective action is defined by

$$
e^{iS_{\text{eff}}[\phi]}
=\int \mathcal D H\,e^{iS[\phi,H]}.
$$

In Euclidean signature this becomes

$$
e^{-S_{E,\text{eff}}[\phi]}
=\int \mathcal D H\,e^{-S_E[\phi,H]}.
$$

The exact $S_{\text{eff}}$ is generally nonlocal. But if all light momenta and masses satisfy $Q\ll M$, the nonlocality is confined to distances of order $M^{-1}$ and can be expanded into local operators:

$$
S_{\text{eff}}[\phi]
=\int d^d x\,\mathcal L_{\text{light}}(\phi)
+\sum_i C_i(M,\mu)\int d^d x\,\mathcal O_i(\phi).
$$

That local expansion is the EFT. Matching determines the Wilson coefficients $C_i$.

The most compact slogan is

$$
\text{integrating out is an operation on degrees of freedom; matching is how its coefficients are fixed.}
$$

The two are closely related, but they are not identical. Integrating out produces an effective action. Matching chooses a convenient local basis and renormalization convention for using it.

## Prerequisites

You should know [Effective Field Theory: Overview](/renormalization-rg-eft/effective-field-theory/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), and [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/).

For the one-loop determinant sections, it is helpful to know [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), and [Functional Renormalization Group Preview](/renormalization-rg-eft/wilsonian-renormalization/functional-renormalization-group-preview/).

## Core idea

A heavy field can influence low-energy physics in three ways:

| Effect | Low-energy description |
|---|---|
| It shifts renormalizable parameters. | Masses, kinetic terms, gauge couplings, Yukawa couplings, vacuum energy. |
| It generates higher-dimension operators. | Local interactions suppressed by powers of $1/M$. |
| It leaves topological or anomalous information. | Wess–Zumino terms, theta terms, Chern–Simons terms, anomaly-matching data. |

The first effect is often called a threshold correction. The second is the usual Wilson-coefficient tower. The third is the warning label: not everything heavy disappears in a naive power expansion.

If the heavy field has mass $M$ and the process uses momenta $Q\ll M$, the heavy propagator is never resolved over long distances. The exact nonlocal kernel can be expanded:

$$
\frac{1}{M^2-\Box}
=\frac{1}{M^2}
+\frac{\Box}{M^4}
+\frac{\Box^2}{M^6}
+\cdots,
$$

with signs adjusted according to Lorentzian or Euclidean convention. Each term is local. The expansion parameter is not mystical; it is $Q^2/M^2$.

## Setup and conventions

This page uses the conventions fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/). We use $H$ for a heavy field of mass $M$ and $\phi$ for light fields with momenta and masses collectively denoted by $Q$.

There are two related but distinct effective actions:

| Object | Definition | Typical use |
|---|---|---|
| Wilsonian effective action | path integral over removed degrees of freedom | EFT Lagrangians, matching, power counting |
| 1PI quantum effective action | Legendre transform of connected generating functional | quantum equations of motion, effective potential, background fields |

This page mostly discusses the Wilsonian low-energy action obtained by removing heavy fields. In perturbative calculations, the same local coefficients can often be extracted from one-particle-irreducible amplitudes or background-field effective actions, provided the IR physics and field normalizations are treated consistently.

When signs matter, Euclidean formulas will be explicitly labeled. Euclidean notation is cleaner for Gaussian integration, while Lorentzian notation is often closer to scattering amplitudes.

## Integrating out versus deleting

Deleting a heavy field from a Lagrangian is not the same as integrating it out.

Suppose the full theory contains

$$
\mathcal L[\phi,H]
=\mathcal L_{\text{light}}[\phi]
+\mathcal L_H[H]
+\mathcal L_{\text{int}}[\phi,H].
$$

The naive deletion rule would be

$$
\mathcal L[\phi,H]\longrightarrow \mathcal L_{\text{light}}[\phi].
$$

That is almost never correct. The correct EFT has

$$
\mathcal L_{\text{EFT}}[\phi]
=\mathcal L_{\text{light}}[\phi]
+\Delta\mathcal L_{\text{threshold}}[\phi]
+\sum_{n>0}\frac{1}{M^n}\mathcal L_n[\phi].
$$

The heavy field no longer appears as an external or internal propagating degree of freedom, but its virtual effects remain in the coefficients of local light-field operators.

Deleting is amnesia. Integrating out is memory compressed into coefficients.

## Tree-level integration

At tree level, integrating out a heavy field means solving its classical equation of motion and substituting back into the action. Consider a heavy scalar $H$ coupled linearly to a light composite source $\mathcal J(\phi)$:

$$
\mathcal L
=\mathcal L_{\text{light}}
+\frac12\partial_\mu H\partial^\mu H
-\frac12M^2H^2
-H\mathcal J.
$$

The heavy-field equation is

$$
(\Box+M^2)H=-\mathcal J.
$$

At low energy,

$$
H_{\text{cl}}
=-\frac{1}{M^2+\Box}\mathcal J
=-\frac{1}{M^2}\mathcal J
+\frac{1}{M^4}\Box\mathcal J
+O\left(\frac{\partial^4}{M^6}\right).
$$

Substitution gives

$$
\Delta\mathcal L_{\text{EFT}}
=\frac12\mathcal J\frac{1}{M^2+\Box}\mathcal J
=\frac{1}{2M^2}\mathcal J^2
-\frac{1}{2M^4}\mathcal J\Box\mathcal J
+O\left(\frac{\partial^4}{M^6}\right).
$$

This is the classical origin of many tree-level Wilson coefficients. It also explains why derivative operators are not optional: they are the next terms in the same heavy-propagator expansion.

## Gaussian path integration

The path integral makes the same logic precise and adds loops. Work in Euclidean signature and suppose the heavy field appears quadratically:

$$
S_E[\phi,H]
=S_{E,\text{light}}[\phi]
+\frac12 H A[\phi] H
+H J[\phi].
$$

Here $A[\phi]$ is a differential operator and $J[\phi]$ is a light-field source. Completing the square gives

$$
S_{E,\text{eff}}[\phi]
=S_{E,\text{light}}[\phi]
-\frac12 J A^{-1}J
+\frac12\operatorname{Tr}\log A
+\text{constant}.
$$

The two important pieces have different meanings:

| Term | Meaning |
|---|---|
| $-\frac12 J A^{-1}J$ | tree-level exchange of the heavy field |
| $\frac12\operatorname{Tr}\log A$ | one-loop determinant of the heavy field |

If the heavy field is a fermion, the determinant has the opposite statistics sign. Schematically,

$$
\Delta S_{E,\text{fermion}}
=-\operatorname{Tr}\log A_F.
$$

These formulas are exact for a Gaussian heavy field. In an interacting theory they become the starting point for loop expansion around the heavy-field saddle.

## One-loop determinants and local expansion

For many applications, the heavy field contributes a one-loop functional determinant of the form

$$
\Delta S_E^{\text{1-loop}}
=\frac12\operatorname{Tr}\log\left[-D^2+M^2+U(\phi)\right],
$$

for a bosonic heavy field. The operator $D_\mu$ may include background gauge and geometric connections, while $U(\phi)$ collects light-field-dependent masses and interactions.

For slowly varying backgrounds, expand in powers of derivatives and $U/M^2$:

$$
\operatorname{Tr}\log\left[-D^2+M^2+U\right]
=
\operatorname{Tr}\log\left[-D^2+M^2\right]
+\operatorname{Tr}\left(\frac{1}{-D^2+M^2}U\right)
-\frac12\operatorname{Tr}\left(\frac{1}{-D^2+M^2}U\right)^2+
\cdots.
$$

After regularization and renormalization, this expansion generates local operators such as

$$
\Delta\mathcal L_{\text{EFT}}
\sim
M^4,
\qquad
M^2\phi^2,
\qquad
F_{\mu\nu}F^{\mu\nu},
\qquad
\frac{1}{M^2}(\partial\phi)^4,
\qquad
\frac{1}{M^2}\phi^2F_{\mu\nu}F^{\mu\nu},
\ldots
$$

The first few terms can renormalize vacuum energy, masses, and marginal couplings. Higher terms are suppressed by powers of $1/M$.

This expansion is the functional version of one-loop matching. Diagram-by-diagram matching and functional determinant matching are two languages for the same short-distance calculation.

## Integrating out particles versus modes

There are two common uses of the phrase "integrate out." They are related, but not identical.

**Integrating out a heavy field** removes an entire particle species or multiplet from the low-energy theory. The heavy field no longer appears in propagators at any momentum.

**Integrating out modes** removes a band of momenta, often for every field. This is the Wilsonian momentum-shell operation:

$$
\phi(p)=\phi_<(p)+\phi_>(p),
\qquad
\Lambda/b<|p|<\Lambda
\quad\text{is integrated out.}
$$

Heavy-field EFT and Wilsonian shell RG share the same spirit: reduce degrees of freedom and compensate by changing the action. But they answer different practical questions.

| Operation | Removes | Typical result |
|---|---|---|
| Integrate out a heavy field | all modes of a massive species | EFT below a mass threshold |
| Integrate out a momentum shell | high-momentum modes of fields still present | Wilsonian RG flow at fixed field content |

In a multi-scale problem, both operations may appear. One may integrate out a heavy particle at $M$, then run the resulting EFT by integrating or renormalizing lower momentum modes.

## Matching after integrating out

The formal path integral

$$
e^{iS_{\text{eff}}[\phi]}
=\int \mathcal D H\,e^{iS[\phi,H]}
$$

does not by itself tell you which operator basis to publish, which renormalization scheme to use, or how to define input parameters. For calculations, one still performs matching:

$$
\mathcal A_{\text{full}}(Q\ll M)
=
\mathcal A_{\text{EFT}}(Q;C_i(\mu),\mu)
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right).
$$

A useful workflow is:

| Step | Action |
|---:|---|
| 1 | Decide which fields are light and remain in the EFT. |
| 2 | Integrate out or compute amplitudes involving the heavy fields. |
| 3 | Expand in $Q/M$. |
| 4 | Express the result in a complete local operator basis. |
| 5 | Use field redefinitions and equations of motion to remove redundancies. |
| 6 | State the renormalization scheme and matching scale. |
| 7 | Run Wilson coefficients to the scale where matrix elements are evaluated. |

The heavy-field path integral gives the raw effective action. Matching turns it into a usable EFT data set.

## Gauge symmetry and heavy fields

Integrating out heavy fields must respect the symmetries of the low-energy theory. This is especially delicate in gauge theories.

If the heavy field transforms under an unbroken gauge symmetry, the low-energy operators must be gauge invariant. Functional methods often use a background-field gauge because it keeps gauge covariance manifest in intermediate expressions. This is not just elegance; it prevents an avalanche of gauge-noncovariant intermediate terms.

If a gauge symmetry is spontaneously broken, one must identify which fields are genuinely heavy and which gauge redundancies remain. Removing a heavy vector boson, for example, produces four-fermion operators and other interactions constrained by the unbroken symmetries. In the electroweak theory, integrating out the $W$ boson at tree level gives the Fermi interaction at low energies.

Anomalies require extra care. A heavy fermion can leave behind Wess–Zumino terms or Chern–Simons terms that preserve anomaly matching. The slogan "heavy particles decouple" does not mean "heavy particles leave no topological memory."

## Nonlocal exact action versus local EFT

The exact effective action after integrating out $H$ is usually nonlocal. For example, the tree-level exchange term

$$
\frac12\mathcal J\frac{1}{M^2+\Box}\mathcal J
$$

is nonlocal if kept exactly. The EFT replaces it by a derivative expansion:

$$
\frac12\mathcal J\frac{1}{M^2+\Box}\mathcal J
=
\frac{1}{2M^2}\mathcal J^2
-\frac{1}{2M^4}\mathcal J\Box\mathcal J+\cdots.
$$

This expansion is valid only below the threshold. If the process can resolve the heavy propagator, the EFT has left its domain of validity. Near $q^2\simeq M^2$, the exact propagator has a pole or resonance structure that no finite local expansion can reproduce.

The local EFT is therefore not a bad approximation to the full theory everywhere. It is a controlled approximation in a specified low-energy domain.

## Example: Fermi theory from heavy W exchange

At energies much smaller than the $W$ mass, charged-current weak interactions are well described by a local four-fermion operator. The full-theory exchange has the schematic structure

$$
\mathcal A_{\text{full}}
\sim
\frac{g^2}{q^2-M_W^2}
J_\mu^+J^{-\mu}.
$$

For $|q^2|\ll M_W^2$,

$$
\frac{g^2}{q^2-M_W^2}
=-\frac{g^2}{M_W^2}\left(1+\frac{q^2}{M_W^2}+\cdots\right).
$$

The leading EFT interaction is therefore a local four-fermion operator,

$$
\mathcal L_{\text{Fermi}}
\sim
-\frac{g^2}{M_W^2}J_\mu^+J^{-\mu},
$$

up to conventional factors in the definition of $G_F$ and the current normalization. Higher terms in the expansion are higher-dimension derivative operators. The $W$ boson is not present in the low-energy theory, but its mass and coupling determine the coefficient of the contact interaction.

## Example: Euler–Heisenberg logic

In QED at energies much below the electron mass, one can integrate out the electron and obtain an effective action for photons alone. Gauge invariance and Lorentz invariance allow terms such as

$$
\Delta\mathcal L_{\text{eff}}
\sim
\frac{\alpha^2}{m_e^4}
\left(F_{\mu\nu}F^{\mu\nu}\right)^2
+
\frac{\alpha^2}{m_e^4}
\left(F_{\mu\nu}\widetilde F^{\mu\nu}\right)^2
+
\cdots.
$$

The electron is absent as a propagating low-energy field, but virtual electron loops generate photon self-interactions. This is a perfect example of the EFT mindset: low-energy photons can scatter, and the coefficient remembers the heavy charged particle that was removed.

The precise numerical coefficients belong in a model calculation. The structural point belongs here: heavy loops generate local gauge-invariant operators.

## When integrating out is unsafe

Integrating out a field is justified only if the low-energy problem cannot resolve it as an active degree of freedom. The procedure is unsafe or incomplete when:

| Situation | Problem |
|---|---|
| $Q\sim M$ | the heavy propagator is not locally expandable |
| near a resonance | finite-width and unstable-particle effects matter |
| heavy and light fields are strongly mixed | the light-heavy split is not diagonal or not stable |
| anomalies are present | topological terms may remain unsuppressed |
| a symmetry is nonlinearly realized | naive deletion can violate the correct low-energy symmetry |
| finite temperature has $T\sim M$ | thermal occupation of the heavy field may matter |
| nonperturbative thresholds appear | no simple perturbative local expansion may exist |

None of these invalidate EFT. They say that the EFT must be chosen with the correct degrees of freedom and expansion parameters.

## Common pitfalls

**Deleting instead of integrating.** Removing a heavy field from the Lagrangian without adding threshold corrections and higher-dimension operators throws away physical information.

**Confusing heavy fields with high momentum.** A heavy field can have low three-momentum and still be off shell by its mass. A light field can have high momentum in a Wilsonian shell. Species and momentum are different classifications.

**Keeping a local expansion near a pole.** The expansion of $1/(M^2-q^2)$ fails near $q^2=M^2$. Resonances are not approximated by a finite number of contact terms.

**Forgetting field redefinitions.** The raw effective action after integrating out a field may contain redundant operators. A published Wilson coefficient is basis dependent.

**Breaking gauge invariance by the split.** Integrating out part of a gauge multiplet or using a noncovariant basis can obscure symmetry. The final EFT must respect the unbroken gauge symmetries.

**Assuming decoupling means no memory.** Heavy particles can leave finite shifts, suppressed operators, and topological or anomalous terms.

## Relations to other pages

[Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/) gives the amplitude and classical equation-of-motion version of the first terms derived here. [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/) explains how heavy-loop effects are separated from EFT loops. [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) focuses on the finite matching terms at $\mu_M\sim M$.

[Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/) and [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/) explain the broader Wilsonian logic. [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/) and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/) explain why the local operator expansion must be quotiented by basis equivalences.

## Research status

The perturbative operation of integrating out heavy fields is standard and foundational. It underlies Fermi theory, chiral perturbation theory, heavy-quark EFT, SMEFT, nonrelativistic EFTs, gravitational EFT, Euler–Heisenberg theory, and many condensed-matter effective descriptions.

The active frontier is not the basic idea but the scale and subtlety of applications: gauge-covariant functional matching, multi-loop determinants, evanescent operators, unstable particles, finite-temperature thresholds, strongly coupled matching, nonperturbative lattice-to-continuum matching, and automated EFT basis reduction.

## Exercises

### Exercise 1: Complete the square

In Euclidean signature, let

$$
S_E[\phi,H]
=S_{E,\text{light}}[\phi]
+\frac12H A H+H J.
$$

Assume $A$ is positive and invertible. Complete the square and derive

$$
S_{E,\text{eff}}[\phi]
=S_{E,\text{light}}[\phi]
-\frac12J A^{-1}J
+\frac12\operatorname{Tr}\log A
+\text{constant}.
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
\frac12H A H+H J
=\frac12(H+A^{-1}J)A(H+A^{-1}J)
-\frac12J A^{-1}J.
$$

Shift the integration variable to $H'=H+A^{-1}J$. The Gaussian integral over $H'$ gives a determinant factor proportional to $(\det A)^{-1/2}$. Therefore

$$
e^{-S_{E,\text{eff}}}
=e^{-S_{E,\text{light}}+\frac12J A^{-1}J}
(\det A)^{-1/2}\times\text{constant}.
$$

Taking minus the logarithm gives

$$
S_{E,\text{eff}}
=S_{E,\text{light}}
-\frac12J A^{-1}J
+\frac12\operatorname{Tr}\log A
+\text{constant}.
$$

</details>

### Exercise 2: Expansion error

Suppose a heavy exchange gives the factor

$$
\frac{1}{M^2-q^2}
$$

with $|q^2|\ll M^2$. Expand through order $q^2/M^4$ and estimate the relative size of the next term.

<details><summary><strong>Solution</strong></summary>

Use the geometric expansion

$$
\frac{1}{M^2-q^2}
=\frac{1}{M^2}\frac{1}{1-q^2/M^2}
=\frac{1}{M^2}\left(1+\frac{q^2}{M^2}+\frac{q^4}{M^4}+\cdots\right).
$$

Through order $q^2/M^4$,

$$
\frac{1}{M^2-q^2}
=\frac{1}{M^2}+\frac{q^2}{M^4}+O\left(\frac{q^4}{M^6}\right).
$$

The next relative correction is of order $q^4/M^4$ compared with the leading term, or of order $q^2/M^2$ compared with the retained derivative correction.

</details>

### Exercise 3: Fermion determinant sign

A real bosonic Gaussian integral gives a factor $(\det A)^{-1/2}$. A Grassmann Gaussian integral gives a factor $\det A_F$. Explain why a heavy fermion contributes $-\operatorname{Tr}\log A_F$ to the Euclidean effective action.

<details><summary><strong>Solution</strong></summary>

For a boson,

$$
\int dH\,e^{-\frac12H A H}\propto (\det A)^{-1/2},
$$

so the effective action receives

$$
+\frac12\operatorname{Tr}\log A.
$$

For Grassmann variables,

$$
\int d\overline\psi\,d\psi\,e^{-\overline\psi A_F\psi}\propto \det A_F.
$$

Since the path integral weight is $e^{-S_{\text{eff}}}$, a multiplicative factor $\det A_F=e^{\operatorname{Tr}\log A_F}$ corresponds to

$$
S_{\text{eff}}\supset -\operatorname{Tr}\log A_F.
$$

The minus sign is the usual closed-fermion-loop statistics sign in functional language.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for effective actions, renormalization, and EFT viewpoints.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on nonrenormalizable theories, RG, effective actions, and EFT examples.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, Wilson actions, decoupling, power counting, and matching.
- Sidney Coleman, *Aspects of Symmetry*, especially lectures on functional methods, renormalization, and effective actions.
- Aneesh V. Manohar, EFT lecture notes, for practical matching and functional methods in modern EFT.

## Version history

- 2026-06-18: First polished draft. Added path-integral definition, Gaussian integration, tree-level elimination, one-loop determinant interpretation, gauge-symmetry caveats, examples, and exercises.
