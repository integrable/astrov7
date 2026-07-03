---
title: "Parameter Counting"
description: "Counts the physically independent parameters of the minimal renormalizable Standard Model and explains how field-basis redundancies reduce raw Yukawa matrices to masses, mixings, and CP phases."
sidebar:
  label: "Parameter Counting"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–91; Schwartz Chs. 29–31; Burgess Ch. 9; Weinberg Vol. II electroweak and Standard Model material."
topics:
  - Standard Model parameters
  - flavor basis
  - Yukawa matrices
  - CKM matrix
  - CP phases
  - QCD theta angle
canonicalTopics:
  - standard-model-parameter-counting
  - standard-model-flavor-parameters
  - ckm-parameter-counting
  - qcd-theta-angle
  - neutrino-parameter-counting
researchStatus:
  established:
    - "The minimal renormalizable Standard Model without neutrino masses has 19 conventional physical parameters when the QCD theta angle is included."
  active:
    - "Observed neutrino masses require extra parameters from either higher-dimensional operators or new fields, and the values and patterns of all flavor parameters remain unexplained by the minimal theory."
---

## Summary

The minimal renormalizable Standard Model is compact, but it is not parameter-free. Once field-basis redundancies are removed, the usual count is

$$
\boxed{19}
$$

physical parameters for the minimal theory **without neutrino masses**, including the QCD theta angle. A convenient decomposition is

$$
19
=
3_{\rm gauge}
+
2_{\rm Higgs}
+
13_{\rm flavor}
+
1_{\rm QCD\ theta}.
$$

The $13$ flavor parameters are

$$
6\text{ quark masses}
+
3\text{ charged-lepton masses}
+
3\text{ CKM angles}
+
1\text{ CKM phase}.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![Standard Model parameter counting flow](/figures/gauge-theories-standard-model/standard-model-parameter-counting-flow.svg)

<figcaption>

The raw Yukawa sector contains three complex $3\times3$ matrices, but many entries are basis choices rather than physical constants. Quotienting by flavor rotations leaves quark masses, charged-lepton masses, CKM angles, and one CKM CP phase. Neutrino masses add extra parameters beyond the minimal renormalizable Standard Model.

</figcaption>
</figure>

The count is a useful diagnostic. It tells you which constants are measured inputs, which phases are removable, and where the minimal theory stops explaining things. It also tells you what changes when neutrino masses are included.

## Prerequisites

You should know [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/), [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/), [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/), [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/), and [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/).

This page counts the minimal renormalizable Standard Model with three generations and no neutrino mass operator. At the end we state how the count changes when neutrino masses are added.

## What counts as a physical parameter?

A physical parameter is a number that cannot be removed by a field redefinition, convention, or basis choice. The raw Lagrangian may contain more symbols than the theory contains observables.

For example, the Yukawa matrices

$$
Y_u,
\qquad
Y_d,
\qquad
Y_e
$$

are arbitrary complex $3\times3$ matrices. That sounds like

$$
3\times(9\text{ complex})=27\text{ complex}=54\text{ real}
$$

numbers. But not all of those numbers are physical. Many are artifacts of how we label the three generations of $Q_L,u_R,d_R,L_L,e_R$.

A useful slogan is:

$$
\text{physical parameters}
=
\text{raw parameters}
-
\text{removable basis choices}.
$$

The subtlety is that unbroken symmetries do **not** remove parameters, because they leave the couplings unchanged. Only broken flavor rotations can be used to simplify the Yukawa matrices.

## Non-flavor parameters

The non-flavor part is straightforward.

The gauge sector has three couplings:

$$
g_s,
\qquad
 g,
\qquad
 g'.
$$

The Higgs potential

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2
$$

has two real parameters:

$$
\mu^2,
\qquad
\lambda.
$$

Equivalently, after electroweak symmetry breaking one can trade them for

$$
v,
\qquad
m_h,
$$

or for other measured electroweak inputs. The count is still two.

Finally, the QCD theta parameter contributes one more physical parameter:

$$
\bar\theta_{\rm QCD}.
$$

Thus the non-flavor count is

$$
3+2+1=6.
$$

This page includes $\bar\theta_{\rm QCD}$ in the minimal count. Some phenomenological lists omit it because its measured value is extremely constrained; that is a numerical statement, not a parameter-counting statement.

## Raw Yukawa data

The charged-fermion Yukawa sector is

$$
\mathcal L_Y
=
-
\bar Q_LY_dHd_R
-
\bar Q_LY_u\widetilde H u_R
-
\bar L_LY_eHe_R
+\mathrm{h.c.}
$$

Each $Y_f$ is a complex $3\times3$ matrix:

$$
Y_f\in\operatorname{Mat}_{3\times3}(\mathbb C).
$$

Therefore

$$
Y_u,Y_d,Y_e:
\qquad
3\times(9\text{ moduli}+9\text{ phases})=54
$$

real raw parameters.

If generations had labels painted on by nature, all of these would be physical. They do not. The kinetic terms and gauge interactions are blind to unitary rotations among generations with identical gauge quantum numbers.

## Flavor-basis redundancy

Before the Yukawa matrices are turned on, the fermion kinetic terms have the flavor symmetry

$$
U(3)_Q\times U(3)_u\times U(3)_d\times U(3)_L\times U(3)_e.
$$

Here each $U(3)$ acts on the three generations of one gauge representation. Since

$$
\dim U(3)=9,
$$

this is a $45$-parameter group of basis changes.

The Yukawa matrices transform as

$$
Y_u\to V_QY_uV_u^\dagger,
\qquad
Y_d\to V_QY_dV_d^\dagger,
\qquad
Y_e\to V_LY_eV_e^\dagger.
$$

These transformations do not change physics; they only change the generation basis.

The Yukawas do not break all of $U(3)^5$. In the minimal Standard Model without neutrino masses, the remaining exact continuous fermion-number symmetries are

$$
U(1)_B\times U(1)_e\times U(1)_\mu\times U(1)_\tau
$$

at the perturbative renormalizable level. These four unbroken symmetries cannot be used to remove Yukawa parameters, because they leave the already-diagonal form unchanged.

Therefore the number of broken flavor-basis directions is

$$
45-4=41.
$$

The physical Yukawa count is then

$$
54-41=13.
$$

That one line is the cleanest group-theoretic count of the Standard Model flavor parameters.

## Quark sector count

The quark Yukawa matrices are $Y_u$ and $Y_d$. They contain

$$
2\times18=36
$$

raw real parameters. The quark kinetic terms have

$$
U(3)_Q\times U(3)_u\times U(3)_d,
$$

which has $27$ parameters. The quark Yukawas preserve baryon number $U(1)_B$, so the broken basis directions are

$$
27-1=26.
$$

Thus the quark sector has

$$
36-26=10
$$

physical parameters.

These are conventionally organized as

$$
6\text{ quark masses}
+
3\text{ CKM angles}
+
1\text{ CKM CP phase}.
$$

In the mass basis,

$$
M_u=\frac{v}{\sqrt2}Y_u,
\qquad
M_d=\frac{v}{\sqrt2}Y_d.
$$

Biunitary diagonalization gives

$$
U_{uL}^\dagger M_uU_{uR}=M_u^{\rm diag},
\qquad
U_{dL}^\dagger M_dU_{dR}=M_d^{\rm diag},
$$

and the charged-current interaction depends on the mismatch

$$
V_{\rm CKM}=U_{uL}^\dagger U_{dL}.
$$

A general $3\times3$ unitary matrix has $3$ angles and $6$ phases. Rephasings of the six quark mass eigenstate fields remove five of those phases; the common baryon-number phase leaves $V_{\rm CKM}$ unchanged. Hence the physical CKM matrix contains

$$
3\text{ angles}+1\text{ phase}.
$$

The CP-violating phase is physical only for three or more generations. With two generations the CKM matrix has one mixing angle and no CP-odd phase.

## Charged-lepton count without neutrino masses

The charged-lepton Yukawa matrix $Y_e$ contains

$$
18
$$

raw real parameters. The lepton kinetic terms, before neutrino masses, have

$$
U(3)_L\times U(3)_e,
$$

with $18$ parameters. Once $Y_e$ is diagonalized, three separate lepton-family numbers remain:

$$
U(1)_e\times U(1)_\mu\times U(1)_\tau.
$$

Thus the number of broken basis directions is

$$
18-3=15,
$$

and the number of physical charged-lepton Yukawa parameters is

$$
18-15=3.
$$

These are just

$$
m_e,
\qquad
m_\mu,
\qquad
m_\tau.
$$

There is no lepton mixing matrix in the minimal renormalizable Standard Model because the neutrinos are massless and the neutrino flavor basis can be rotated along with the charged leptons. The observed PMNS matrix appears only after neutrino masses are added.

## The minimal total

Putting the pieces together:

| Sector | Physical parameters |
|---|---:|
| Gauge couplings $g_s,g,g'$ | $3$ |
| Higgs potential | $2$ |
| Quark masses | $6$ |
| Charged-lepton masses | $3$ |
| CKM angles | $3$ |
| CKM CP phase | $1$ |
| QCD theta angle $\bar\theta$ | $1$ |
| **Total** | **$19$** |

Equivalently,

$$
3+2+6+3+3+1+1=19.
$$

This is the standard count for the minimal renormalizable Standard Model with three generations and massless neutrinos.

## Alternative input choices

The parameter count does not depend on which input scheme is used. For example, instead of using

$$
g,
\qquad
 g',
\qquad
 v,
$$

one often uses experimentally convenient quantities such as

$$
\alpha_{\rm em},
\qquad
G_F,
\qquad
m_Z,
$$

or similar electroweak input sets. These are changes of coordinates on parameter space, not changes in the number of physical parameters.

Likewise, the Higgs potential can be parameterized by

$$
\mu^2,
\lambda,
$$

or by

$$
v,m_h.
$$

At tree level these are related by

$$
v^2=\frac{\mu^2}{\lambda},
\qquad
m_h^2=2\lambda v^2.
$$

Beyond tree level, input schemes and renormalization schemes matter for precision calculations, but the underlying number of independent physical inputs remains the same.

## Neutrino masses change the count

The minimal renormalizable Standard Model has no neutrino masses. Nature does. Therefore the physical theory at low energies must include either higher-dimensional operators or additional fields.

If neutrino masses come from the dimension-five Majorana Weinberg operator, the low-energy lepton sector contains

$$
3\text{ charged-lepton masses}
+
3\text{ neutrino masses}
+
3\text{ PMNS angles}
+
3\text{ leptonic CP phases}.
$$

The three CP phases consist of one Dirac-type phase and two Majorana phases. Compared with the minimal massless-neutrino Standard Model, this adds

$$
3+3+3=9
$$

new physical parameters. Including $\bar\theta_{\rm QCD}$, the low-energy count becomes

$$
19+9=28.
$$

If instead neutrinos are Dirac particles with three added right-handed neutrinos and lepton number is conserved, the neutrino sector adds

$$
3\text{ masses}
+
3\text{ PMNS angles}
+
1\text{ Dirac CP phase}
=7
$$

parameters beyond the minimal count, giving

$$
19+7=26.
$$

These are not contradictions. They are different theories beyond the minimal renormalizable Standard Model.

## Why the QCD theta angle is special

The QCD topological term is

$$
\frac{\theta_3g_s^2}{32\pi^2}G^A_{\mu\nu}\widetilde G^{A\mu\nu}.
$$

A chiral redefinition of quark fields can shift $\theta_3$, but it also changes the phase of the quark mass determinant. The invariant physical combination is conventionally written as

$$
\bar\theta=\theta_3+\arg\det(M_uM_d),
$$

up to sign conventions. This parameter violates CP unless it is zero or extremely small. Its small observed value is the strong CP problem.

The phrase “19 parameters” usually includes $\bar\theta$, even though many phenomenological summaries focus on the 18 parameters that are directly involved in perturbative collider and flavor calculations. Both usages occur; the safer convention is to state explicitly whether $\bar\theta$ is included. Here it is included.

## General generation formulas

For $N$ generations of quarks, the CKM sector contains

$$
N(N-1)/2
$$

mixing angles and

$$
(N-1)(N-2)/2
$$

CP-violating phases. The quark flavor count is

$$
2N
+
\frac{N(N-1)}{2}
+
\frac{(N-1)(N-2)}{2}.
$$

For $N=3$, this gives

$$
6+3+1=10.
$$

For Majorana neutrinos, the lepton mixing matrix has

$$
N(N-1)/2
$$

angles and

$$
N(N-1)/2
$$

physical phases. For $N=3$, this gives three PMNS angles and three phases.

This explains a charmingly annoying fact: CP violation in flavor physics is not generic for one or two generations. Three generations are the first case where a CKM phase cannot be rephased away.

## Common mistakes

**Counting raw Yukawa entries as physical.** Three complex Yukawa matrices contain $54$ real entries, but $41$ of them are removed by field-basis choices. The physical charged-fermion flavor sector has $13$ parameters, not $54$.

**Forgetting unbroken symmetries.** When subtracting field redefinitions, do not subtract transformations that leave the Yukawa matrices invariant. This is why the subtraction is $45-4$, not $45$.

**Confusing input schemes with parameter count.** Using $G_F,m_Z,\alpha_{\rm em}$ instead of $g,g',v$ changes coordinates, not physics.

**Mixing minimal and neutrino-mass Standard Models.** The minimal renormalizable Standard Model has massless neutrinos. Adding the Weinberg operator or right-handed neutrinos changes the parameter count.

**Dropping theta without saying so.** It is common to ignore $\bar\theta$ in collider calculations, but parameter-counting statements should say whether it is included.

## Exercises

### Exercise 1: Quark flavor count

Use the flavor symmetry $U(3)_Q\times U(3)_u\times U(3)_d$ to show that the quark Yukawa sector has $10$ physical parameters.

<details><summary><strong>Solution</strong></summary>

The matrices $Y_u$ and $Y_d$ are two complex $3\times3$ matrices, so they contain

$$
2\times18=36
$$

real raw parameters. The flavor group has

$$
3\times\dim U(3)=3\times9=27
$$

parameters. The quark Yukawas preserve baryon number $U(1)_B$, so only

$$
27-1=26
$$

basis directions are broken and removable. Therefore

$$
36-26=10.
$$

These are $6$ quark masses, $3$ CKM angles, and $1$ CKM phase.

</details>

### Exercise 2: CKM phases for two generations

Use the formula

$$
\frac{(N-1)(N-2)}{2}
$$

for the number of CKM CP phases to show that two generations cannot have CKM CP violation.

<details><summary><strong>Solution</strong></summary>

For $N=2$,

$$
\frac{(N-1)(N-2)}{2}
=
\frac{1\cdot0}{2}=0.
$$

The two-generation CKM matrix has one mixing angle and no physical CP-violating phase. This is why the existence of three generations is essential for CKM CP violation.

</details>

### Exercise 3: Minimal versus Majorana-neutrino count

Starting from the $19$-parameter minimal count, add the low-energy Majorana-neutrino parameters from the Weinberg operator.

<details><summary><strong>Solution</strong></summary>

Majorana neutrino masses add

$$
3\text{ neutrino masses}
+
3\text{ PMNS angles}
+
3\text{ leptonic CP phases}
=9
$$

parameters beyond the massless-neutrino minimal Standard Model. Therefore

$$
19+9=28.
$$

The three leptonic phases are one Dirac-type phase plus two Majorana phases.

</details>

## Relations to other pages

- [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/) identifies the couplings being counted.
- [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/) explains biunitary diagonalization and basis changes.
- [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/) explains why quark mixing leaves three angles and one phase.
- [CP Violation](/gauge-theories-standard-model/flavor-neutrinos/cp-violation/) explains basis-invariant CP tests such as the Jarlskog invariant.
- [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/) and [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) explain how neutrino masses change the lepton parameter count.
- [Theta Angle and Strong CP Problem](/gauge-theories-standard-model/qcd/theta-angle-and-strong-cp-problem/) explains the QCD theta term in more detail.
- [Accidental Symmetries](/gauge-theories-standard-model/standard-model/accidental-symmetries/) explains how the same dimension-four operator list automatically conserves baryon and lepton numbers.
- [Mass Spectrum and Couplings](/gauge-theories-standard-model/standard-model/mass-spectrum-and-couplings/) uses these parameters in the broken-phase mass and coupling dictionary.

## Research status

The parameter count is settled once one specifies the theory being counted. What remains unexplained is the **pattern** of the parameters: the hierarchies of Yukawa eigenvalues, CKM angles, the origin and size of neutrino masses, the smallness of $\bar\theta$, and the values of Higgs-sector parameters. The Standard Model tells us where these numbers enter. It does not tell us why these are the numbers nature chose.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the Standard Model gauge/Higgs, lepton, quark, and neutrino-mass sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction, CP-violation, anomaly, and precision-test chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory and the dimension-five neutrino-mass operator.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for Standard Model flavor, electroweak structure, and CP-violating parameters.
- Coleman, *Aspects of Symmetry*, especially the lectures on symmetries, currents, and hidden symmetry for the conceptual background behind field redefinitions and spontaneous breaking.

## Version history

- **2026-06-19:** Added forward links to accidental symmetries and the mass-spectrum page.
- **2026-06-19:** Initial page counting the minimal Standard Model parameters, basis redundancies, CKM structure, theta angle, and neutrino-mass extensions.
