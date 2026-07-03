---
title: "CP Violation"
description: "Explains CP violation in the Standard Model quark sector, emphasizing CKM rephasing invariants, the Jarlskog invariant, and the distinction between physical phases and basis artifacts."
sidebar:
  label: "CP Violation"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77 and §§88–91; Schwartz Chs. 29–30; Coleman, Aspects of Symmetry, Chs. 3–5; Burgess Ch. 9."
topics:
  - CP violation
  - CKM phase
  - Jarlskog invariant
  - flavor rephasings
  - quark Yukawa matrices
canonicalTopics:
  - ckm-cp-violation
  - jarlskog-invariant
  - rephasing-invariant-cp-phase
  - flavor-basis-invariants
  - standard-model-cp-violation
researchStatus:
  established:
    - "With three nondegenerate quark generations, the Standard Model contains one physical CP-violating phase in the CKM matrix."
  active:
    - "The origin of the CKM phase, the strong CP problem, and the insufficiency of Standard Model CP violation for baryogenesis motivate physics beyond the minimal Standard Model."
---

## Summary

CP violation in the Standard Model quark sector is the statement that no allowed quark flavor-basis choice can make all charged-current mixing amplitudes simultaneously real. In the mass basis, this appears as one irreducible complex phase in the CKM matrix.

A useful rephasing-invariant measure is the Jarlskog invariant,

$$
J
=
\operatorname{Im}
\left(
V_{ij}V_{kl}V_{il}^*V_{kj}^*
\right),
\qquad
i\ne k,\quad j\ne l.
$$

For three generations, all such nonzero choices have the same magnitude, up to signs fixed by the ordering of indices. In the standard CKM parametrization,

$$
J
=
c_{12}c_{23}c_{13}^2s_{12}s_{23}s_{13}\sin\delta.
$$

Thus CKM CP violation requires all three mixing angles to be nonzero and the physical phase $\delta$ not to be $0$ or $\pi$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![CP violation as a rephasing-invariant obstruction](/figures/gauge-theories-standard-model/cp-violation-invariant-map.svg)

<figcaption>

Complex Yukawa matrices do not automatically mean physical CP violation. Flavor rotations and quark rephasings remove basis artifacts. The surviving quark-sector CP violation is captured by rephasing-invariant quantities such as $J$ or, equivalently, commutator invariants built from $H_u=M_uM_u^\dagger$ and $H_d=M_dM_d^\dagger$.

</figcaption>
</figure>

The core lesson is brutal and beautiful: **CP violation is not “there is an $i$ in the Lagrangian.” It is “there is no allowed field basis in which the relevant couplings are all real.”**

## Prerequisites

You should know [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/) and [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/). You should also know that the charged weak current in the quark mass basis is

$$
\mathcal L_{Wqq}
=
-\frac{g}{\sqrt2}
\left(
W_\mu^+\bar u_L\gamma^\mu Vd_L
+
W_\mu^-\bar d_L\gamma^\mu V^\dagger u_L
\right).
$$

This page focuses on the CKM source of CP violation. It does not replace the anomaly and theta-angle pages. In particular, the QCD theta term is a separate possible source of CP violation and belongs to [Theta Angle and Strong CP Problem](/gauge-theories-standard-model/qcd/theta-angle-and-strong-cp-problem/).

## What CP means here

The operation CP exchanges particles with antiparticles and flips spatial orientation. For a charged-current amplitude, the essential flavor effect is complex conjugation of the CKM coefficient:

$$
V_{ij}\longleftrightarrow V_{ij}^*.
$$

If every CKM element could be made real by rephasing the quark mass eigenstates, then the charged-current quark sector would conserve CP. If some complex phase remains after all allowed rephasings, CP is violated.

The word **allowed** is doing real work. A field redefinition that preserves kinetic terms and diagonal masses is not a new physical operation; it is a change of labels. Individual phases of CKM entries are therefore not directly meaningful. Only rephasing-invariant combinations can diagnose CP violation.

## Rephasing and invariant quartets

Mass eigenstate quarks may be rephased as

$$
u_i\to e^{i\alpha_i}u_i,
\qquad
d_j\to e^{i\beta_j}d_j.
$$

The CKM entries transform as

$$
V_{ij}\to e^{-i\alpha_i}V_{ij}e^{i\beta_j}.
$$

A single matrix element is not invariant. A product such as

$$
V_{ij}V_{kl}V_{il}^*V_{kj}^*
$$

is invariant, because the phases cancel:

$$
e^{-i\alpha_i}e^{i\beta_j}
e^{-i\alpha_k}e^{i\beta_l}
e^{i\alpha_i}e^{-i\beta_l}
e^{i\alpha_k}e^{-i\beta_j}
=1.
$$

Its imaginary part is a CP-odd invariant. For three generations, a representative choice is

$$
J
=
\operatorname{Im}
\left(
V_{ud}V_{cs}V_{us}^*V_{cd}^*
\right).
$$

Different choices with distinct up-type and down-type indices give $+J$, $-J$, or $0$, depending on the index order and whether indices repeat.

## Why three generations are necessary

The previous page counted physical phases in an $N$-generation CKM matrix:

$$
N_{\rm phases}
=
\frac{(N-1)(N-2)}{2}.
$$

For $N=1$ and $N=2$, this number vanishes. With two generations, the quark mixing matrix can be made real by field rephasings. The Cabibbo angle gives flavor mixing, but not CKM CP violation.

For $N=3$, the phase count gives one physical phase. This was the Kobayashi–Maskawa observation: a renormalizable weak interaction with quarks can violate CP through charged-current mixing if there are at least three generations.

In the standard three-generation parametrization,

$$
J
=
c_{12}c_{23}c_{13}^2s_{12}s_{23}s_{13}\sin\delta.
$$

This formula makes several conditions transparent:

- if any mixing angle is zero, $J=0$;
- if $\delta=0$ or $\pi$, $J=0$;
- if one generation decouples, $J=0$.

Mixing alone is not CP violation. A complex phase alone is not enough if it can be rephased away. CP violation is the invariant coexistence of mixing and a non-removable phase.

## Jarlskog commutator invariant

The CKM phase can also be detected before choosing a mass basis. Define the Hermitian matrices

$$
H_u=M_uM_u^\dagger,
\qquad
H_d=M_dM_d^\dagger.
$$

Under a common left-handed quark flavor rotation,

$$
H_u\to W_QH_uW_Q^\dagger,
\qquad
H_d\to W_QH_dW_Q^\dagger.
$$

The commutator

$$
[H_u,H_d]=H_uH_d-H_dH_u
$$

therefore transforms by conjugation, so traces and determinants built from it are basis invariant. For three generations, a standard CP-odd invariant is

$$
\operatorname{Tr}\left([H_u,H_d]^3\right).
$$

Up to an overall sign fixed by the ordering convention for mass eigenvalues,

$$
\operatorname{Tr}\left([H_u,H_d]^3\right)
=
6iJ
\prod_{a<b}(m_{u_a}^2-m_{u_b}^2)
\prod_{c<d}(m_{d_c}^2-m_{d_d}^2).
$$

This formula is wonderfully merciless. CP violation vanishes not only when $J=0$, but also when two up-type quarks or two down-type quarks are exactly degenerate. Degeneracy gives an extra flavor rotation inside the degenerate subspace, and that extra freedom can remove the would-be CP phase.

The commutator view also clarifies why CP violation is tied to noncommuting mass structures. If $H_u$ and $H_d$ commute, they can be diagonalized by the same left-handed rotation; then $V_{\rm CKM}$ can be made trivial and no CKM CP violation remains.

## CP violation versus complex notation

A complex coupling is not automatically CP violation. Consider a single-generation Yukawa term,

$$
-y\,\bar Q_L\tilde H u_R+\mathrm{h.c.}
$$

If $y=|y|e^{i\phi}$, the phase can be removed by rephasing $u_R$. The resulting mass is real and positive. No physical CP violation follows from the original complex number.

With multiple generations, there are many complex entries in $Y_u$ and $Y_d$. Most phases are still basis artifacts. The physical question is whether all phases can be removed simultaneously while preserving the canonical kinetic terms and diagonal positive masses. For three quark generations, one CKM phase cannot be removed in general.

A good diagnostic sentence is:

> CP is conserved if there exists a flavor basis in which the quark Yukawa matrices are real.

Equivalently, the CP-odd invariants vanish. For three nondegenerate generations, $J=0$ is the essential CKM condition.

## How CP-odd observables arise

At the level of amplitudes, CP asymmetries require interference. A schematic decay amplitude may have two contributions,

$$
\mathcal A
=
A_1e^{i\delta_1^{\rm strong}}e^{i\phi_1^{\rm weak}}
+
A_2e^{i\delta_2^{\rm strong}}e^{i\phi_2^{\rm weak}}.
$$

The CP-conjugate amplitude has the weak phases conjugated,

$$
\bar{\mathcal A}
=
A_1e^{i\delta_1^{\rm strong}}e^{-i\phi_1^{\rm weak}}
+
A_2e^{i\delta_2^{\rm strong}}e^{-i\phi_2^{\rm weak}},
$$

while strong phases are not conjugated in the same way because they come from CP-even final-state interactions. A direct rate asymmetry is proportional to

$$
\sin(\phi_1^{\rm weak}-\phi_2^{\rm weak})
\sin(\delta_1^{\rm strong}-\delta_2^{\rm strong})
$$

in this two-amplitude cartoon.

This formula is not the whole theory of kaons or $B$ mesons, but it captures the main logic. CP-odd phases become observable when at least two paths to the same final state interfere and cannot be made simultaneously real.

## Unitarity triangles and the area test

A unitarity relation such as

$$
V_{ud}V_{ub}^*
+
V_{cd}V_{cb}^*
+
V_{td}V_{tb}^*
=0
$$

forms a triangle in the complex plane. The area of any CKM unitarity triangle is

$$
\frac{|J|}{2}.
$$

If $J=0$, the triangle collapses to a line. If $J\ne0$, the triangle has nonzero area and CKM CP violation is present.

This geometric picture is useful because it separates convention-dependent phases from invariant geometry. Rephasing quark fields rotates or reflects how individual sides are drawn, but it cannot change the area.

## CKM CP violation and the strong CP problem

The Standard Model has another possible source of CP violation: the QCD theta term,

$$
\mathcal L_\theta
=
\frac{g_s^2\theta}{32\pi^2}
G_{\mu\nu}^a\tilde G^{a\mu\nu}.
$$

This is not CKM CP violation. It is a separate operator in the strong-interaction sector. Experimental constraints imply that the effective strong CP angle is extremely small, which is the strong CP problem. The CKM phase does not solve it.

Conversely, setting $\theta=0$ does not remove CKM CP violation. The two issues are logically distinct even though both involve CP.

## CKM CP violation and baryogenesis

The Standard Model contains CP violation through the CKM phase, and it violates baryon plus lepton number nonperturbatively through electroweak anomaly effects. Nevertheless, the minimal Standard Model does not provide a successful explanation of the observed cosmic baryon asymmetry. The CKM source is too suppressed in the relevant electroweak plasma context, and the electroweak transition with the observed Higgs mass is not strongly first order.

This failure is not a failure of CKM as a laboratory description of quark CP violation. It is a statement about cosmology and out-of-equilibrium electroweak dynamics. Many beyond-Standard-Model scenarios add new CP phases precisely because the CKM phase is not enough for baryogenesis.

## Common pitfalls

**Calling any complex Yukawa entry CP violation.** A complex entry may disappear after a flavor rotation or field rephasing. CP violation requires a basis-invariant obstruction.

**Thinking two generations could have CKM CP violation.** Two generations can mix, but the mixing matrix can be made real. Three generations are required for a physical CKM phase.

**Confusing weak phases with strong phases.** Weak phases change sign under CP; strong final-state phases are CP-even. Direct rate asymmetries need both kinds of phase difference.

**Forgetting quark mass degeneracies.** If same-charge quarks are exactly degenerate, extra rotations become available and the Jarlskog commutator invariant vanishes.

**Mixing CKM CP violation with the theta angle.** The CKM phase and the QCD theta term are different sources of CP violation.

**Using one phase convention as if it were physical.** The phase $\delta$ in the standard parametrization is convenient. The invariant physics is in $J$ and related rephasing-invariant quantities.

## Relations to other pages

This page follows [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/). The lepton-sector analogue continues in [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/), where Dirac and possible Majorana phases must be distinguished.

The QCD theta-angle issue is treated in [Theta Angle and Strong CP Problem](/gauge-theories-standard-model/qcd/theta-angle-and-strong-cp-problem/). Gauge anomalies and baryon/lepton number violation appear later in the Standard Model consistency chapter.

## Research status

CKM CP violation is experimentally established and theoretically embedded in the Standard Model. The open questions are not whether the CKM mechanism exists, but why the flavor parameters have their observed values, whether additional CP-violating phases exist, and how CP violation fits into the origin of matter–antimatter asymmetry.

The minimal Standard Model contains CP violation but does not explain the flavor pattern or the baryon asymmetry. So flavor remains both a precision triumph and a conceptual sore tooth.

## Exercises

### Exercise 1: Show that the quartet is rephasing invariant

Under $u_i\to e^{i\alpha_i}u_i$ and $d_j\to e^{i\beta_j}d_j$, show that $V_{ij}V_{kl}V_{il}^*V_{kj}^*$ is invariant.

<details><summary><strong>Solution</strong></summary>

The CKM element transforms as

$$
V_{ij}\to e^{-i\alpha_i}V_{ij}e^{i\beta_j}.
$$

Therefore

$$
V_{ij}V_{kl}V_{il}^*V_{kj}^*
\to
e^{-i\alpha_i+i\beta_j}
e^{-i\alpha_k+i\beta_l}
e^{i\alpha_i-i\beta_l}
e^{i\alpha_k-i\beta_j}
V_{ij}V_{kl}V_{il}^*V_{kj}^*.
$$

The phase factor is $1$, so the product and its imaginary part are invariant.

</details>

### Exercise 2: Read CP violation from the standard parametrization

Use

$$
J=c_{12}c_{23}c_{13}^2s_{12}s_{23}s_{13}\sin\delta
$$

to list three ways CKM CP violation can disappear.

<details><summary><strong>Solution</strong></summary>

The invariant $J$ vanishes if any mixing angle is zero, because then one of $s_{12},s_{23},s_{13}$ is zero. It also vanishes if $\sin\delta=0$, meaning $\delta=0$ or $\pi$ in this parametrization. It also vanishes if the parametrization effectively reduces to fewer than three coupled generations, which is reflected by at least one mixing angle being zero.

</details>

### Exercise 3: Explain the role of mass degeneracy

Use the commutator invariant

$$
\operatorname{Tr}\left([H_u,H_d]^3\right)
\propto
J
\prod_{a<b}(m_{u_a}^2-m_{u_b}^2)
\prod_{c<d}(m_{d_c}^2-m_{d_d}^2)
$$

to explain why exact degeneracy of two up-type quarks removes CKM CP violation.

<details><summary><strong>Solution</strong></summary>

If two up-type quarks have equal mass, then one factor in

$$
\prod_{a<b}(m_{u_a}^2-m_{u_b}^2)
$$

vanishes. Therefore the CP-odd invariant vanishes. Physically, exact degeneracy gives an additional unitary freedom to rotate the degenerate quarks without changing the diagonal mass matrix. That extra freedom can remove the apparent CP-violating phase.

</details>

### Exercise 4: Why one complex phase is not enough language

Explain why saying “the CKM matrix has a complex entry” is not a basis-independent statement.

<details><summary><strong>Solution</strong></summary>

A quark field rephasing changes

$$
V_{ij}\to e^{-i\alpha_i}V_{ij}e^{i\beta_j}.
$$

Thus the phase of an individual entry can be changed by redefining the mass eigenstate fields. Only combinations in which these rephasing factors cancel are invariant. Therefore an individual complex entry is convention-dependent, while quantities such as $J=\operatorname{Im}(V_{ij}V_{kl}V_{il}^*V_{kj}^*)$ are physical.

</details>

## Where to go next

Continue to [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/) to see how the same basis-mismatch logic appears in the lepton sector once neutrinos have mass. Then read [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) for the minimal Standard-Model-field-content operator that generates Majorana neutrino masses.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§75–77 for anomalies and fermion path-integral phases, and §§88–91 for Standard Model flavor sectors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 29–30 for weak interactions, CP violation, and gauge anomalies.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9 for the Standard Model as an EFT and anomaly/flavor context.

### Deeper references

- Kobayashi and Maskawa, “CP-Violation in the Renormalizable Theory of Weak Interaction,” for the three-generation origin of CKM CP violation.
- Jarlskog, “Commutator of the Quark Mass Matrices in the Standard Electroweak Model and a Measure of Maximal CP Nonconservation,” for the basis-invariant formulation.
- Branco, Lavoura, and Silva, *CP Violation*, for a full treatment of CP transformations, rephasing invariants, and flavor phenomenology.
- Coleman, *Aspects of Symmetry*, for classic lectures on symmetry, currents, and spontaneous symmetry breaking.

## Version history

- **2026-06-19:** Added forward links to PMNS Matrix and Weinberg Operator.
- **2026-06-19:** Initial page. Added CP transformation logic, rephasing-invariant quartets, Jarlskog invariant, commutator invariant, relation to unitarity triangles, distinction from strong CP, exercises, and CP-invariant map figure.
