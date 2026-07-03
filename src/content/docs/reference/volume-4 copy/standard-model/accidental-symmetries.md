---
title: "Accidental Symmetries"
description: "Explains why baryon number, lepton number, and related selection rules emerge accidentally in the renormalizable Standard Model, how anomalies qualify them, and how higher-dimensional operators can violate them."
sidebar:
  label: "Accidental Symmetries"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77, §§87–91; Schwartz Chs. 29–31; Burgess Ch. 9; Coleman, symmetry and Higgs lectures."
topics:
  - accidental symmetries
  - baryon number
  - lepton number
  - electroweak anomaly
  - sphalerons
  - proton decay
  - Weinberg operator
canonicalTopics:
  - standard-model-accidental-symmetries
  - baryon-number
  - lepton-number
  - b-minus-l
  - electroweak-sphalerons
  - proton-decay-operators
researchStatus:
  established:
    - "In the minimal renormalizable Standard Model, baryon number and lepton numbers are not imposed as gauge symmetries but follow from Lorentz invariance, gauge invariance, field content, and operator dimension at the classical dimension-four level."
  active:
    - "The observed neutrino masses and the matter–antimatter asymmetry require physics beyond this minimal accidental-symmetry story, usually described by higher-dimensional operators or extra fields."
---

## Summary

An **accidental symmetry** is a symmetry that the low-dimension Lagrangian has even though we did not impose it as a fundamental principle. The minimal renormalizable Standard Model is full of them. The most famous are baryon number and lepton number.

The statement is not

$$
\text{we demanded }B\text{ and }L.
$$

The statement is

$$
\text{Lorentz invariance}
+
\text{SM gauge invariance}
+
\text{SM field content}
+
\dim\mathcal O\le4
\quad\Longrightarrow\quad
B\text{ and }L\text{ conservation classically}.
$$

That is a remarkable filter. It explains why proton decay is absent from the renormalizable Standard Model and why neutrino masses require either new fields or higher-dimensional operators.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Accidental symmetry filter](/figures/gauge-theories-standard-model/standard-model-accidental-symmetry-filter.svg)

<figcaption>

Accidental symmetries are selection rules produced by a filter, not by decree. The renormalizable Standard Model accidentally conserves baryon number and lepton numbers at the classical dimension-four level. Electroweak anomalies, neutrino-mass operators, and dimension-six baryon-violating operators show how the selection rules can fail outside that narrow filter.

</figcaption>
</figure>

The word “accidental” does not mean “unimportant.” Accidental symmetries are often the most physically visible symmetries of an effective field theory. Their violation is a microscope for heavier physics.

## Prerequisites

You should know the [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/), [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/), and [Parameter Counting](/gauge-theories-standard-model/standard-model/parameter-counting/). The discussion also uses the EFT logic from [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) and the anomaly language developed later in the Anomalies and Consistency chapter.

We use the convention

$$
Q=T^3+Y,
$$

and the minimal one-generation fermion content

$$
Q_L,\qquad u_R,\qquad d_R,\qquad L_L,\qquad e_R.
$$

There is no right-handed neutrino field in the minimal renormalizable Standard Model.

## What “accidental” means

Suppose we write the most general local Lagrangian satisfying four requirements:

1. Lorentz invariance;
2. gauge invariance under the Standard Model gauge group;
3. the minimal Standard Model field content;
4. operator dimension at most four.

Then the allowed terms are precisely the gauge kinetic terms, fermion kinetic terms, Higgs kinetic term, Higgs potential, and Yukawa couplings:

$$
\mathcal L_{\rm SM}^{\rm min}
=
\mathcal L_{\rm gauge}
+
\mathcal L_{\rm fermion}
+
\mathcal L_H
+
\mathcal L_Y
+
\mathcal L_\theta.
$$

None of these terms violates baryon number. None of these terms violates total lepton number. With massless neutrinos and after diagonalizing the charged-lepton Yukawa matrix, the minimal theory also preserves separate charged-lepton family numbers.

So the renormalizable Standard Model has selection rules that were not put in by hand:

$$
U(1)_B\times U(1)_{L_e}\times U(1)_{L_\mu}\times U(1)_{L_\tau}
$$

at the classical perturbative level. In a basis-independent discussion before diagonalizing the charged leptons, it is often cleaner to emphasize total lepton number $U(1)_L$ and the flavor-symmetry structure broken by Yukawa matrices.

The proton is therefore stable in the minimal renormalizable Standard Model not because “proton stability” was imposed as a sacred law, but because the renormalizable gauge-invariant operator list has no place to put proton decay. The symmetry is an output of the operator classification. EFT doing EFT things. Very smug, but very useful.

## Baryon number

Assign baryon number

$$
B(Q_L)=B(u_R)=B(d_R)=\frac13,
$$

and

$$
B(L_L)=B(e_R)=B(H)=0.
$$

The factor $1/3$ is conventional and makes a color-singlet three-quark baryon have $B=1$.

At the classical dimension-four level, the baryon current is schematically

$$
J_B^\mu
=
\frac13\sum_{\text{quarks }q}\bar q\gamma^\mu q,
$$

where the sum runs over all quark flavors and colors. The Standard Model gauge interactions preserve it because gluons, $W$ bosons, $B_\mu$, and the Higgs carry no baryon number. The Yukawa interactions preserve it because each Yukawa term contains one quark field and one conjugate quark field.

For example, the down-type Yukawa interaction has the schematic form

$$
\bar Q_L H Y_d d_R+\text{h.c.}
$$

The baryon number is

$$
B(\bar Q_L)+B(H)+B(d_R)
=
-\frac13+0+\frac13=0.
$$

The same cancellation occurs for $Y_u$.

The important point is that baryon number is **not gauged** in the minimal Standard Model. It is a global selection rule of the renormalizable Lagrangian. That distinction matters because global accidental symmetries are not expected to be exact in arbitrary ultraviolet completions.

## Lepton numbers

Assign total lepton number

$$
L(L_L)=L(e_R)=1,
$$

and

$$
L(Q_L)=L(u_R)=L(d_R)=L(H)=0.
$$

The classical lepton current is schematically

$$
J_L^\mu
=
\sum_{\text{leptons }\ell}\bar\ell\gamma^\mu\ell.
$$

The charged-lepton Yukawa term

$$
\bar L_L H Y_e e_R+\text{h.c.}
$$

has

$$
L(\bar L_L)+L(H)+L(e_R)
=
-1+0+1=0.
$$

Thus total lepton number is preserved by the renormalizable Lagrangian.

If the minimal Standard Model has no neutrino mass operator, then one can diagonalize $Y_e$ and define separate lepton family numbers

$$
L_e,\qquad L_\mu,\qquad L_\tau.
$$

These are exact in the minimal massless-neutrino theory. Once neutrino masses and PMNS mixing are included, the separate family numbers are no longer exact. For Majorana neutrino masses, even total lepton number is broken.

This is the clean conceptual lesson:

$$
\text{massless-neutrino minimal SM}
\quad\text{has more accidental lepton symmetry than nature uses.}
$$

Observed neutrino oscillations are already telling us that the minimal accidental lepton-number story is incomplete.

## The flavor symmetry behind the accident

Before turning on Yukawa matrices, the fermion kinetic terms have a large global flavor symmetry. For three generations, ignoring gauge anomalies for the moment,

$$
G_{\rm flavor}
=
U(3)_Q\times U(3)_u\times U(3)_d\times U(3)_L\times U(3)_e.
$$

The Yukawa matrices

$$
Y_u,\qquad Y_d,\qquad Y_e
$$

break this symmetry. Treating them as spurions is often the cleanest way to track which flavor symmetries survive.

A generic pair $Y_u,Y_d$ leaves only total baryon number in the quark sector. This is why the CKM matrix appears: the up- and down-quark Yukawa matrices cannot generally be diagonalized by the same left-handed rotation.

In the lepton sector of the minimal theory, there is only $Y_e$. Because there is no neutrino mass matrix, the charged-lepton Yukawa can be diagonalized without creating a physical lepton-mixing matrix. This leaves separate charged-lepton family numbers. Add the Weinberg operator, and this changes.

So the phrase “lepton family number” is a little more fragile than “baryon number.” It depends on which neutrino-mass terms are included.

## Anomaly qualification: classical is not exact

The previous statements are classical statements about the renormalizable Lagrangian. Quantum mechanically, global currents can be anomalous.

The electroweak $SU(2)_L$ anomaly violates baryon number and lepton number nonperturbatively. For a topological transition with integer charge $n_{\rm top}$,

$$
\Delta B=\Delta L=N_g n_{\rm top},
$$

where $N_g=3$ is the number of generations. Therefore

$$
\Delta(B+L)=2N_g n_{\rm top},
\qquad
\Delta(B-L)=0.
$$

The combination $B-L$ is preserved by the Standard Model gauge anomaly, while $B+L$ is not.

At zero temperature these processes are exponentially suppressed in ordinary low-energy experiments. At high temperature, electroweak sphaleron transitions can be important. This is why baryogenesis and leptogenesis discussions care deeply about whether a proposed mechanism creates $B-L$ or only $B+L$.

:::note[What the anomaly does and does not say]
The anomaly does not mean perturbative proton decay appears in the minimal Standard Model. It means the global currents $J_B^\mu$ and $J_L^\mu$ are not exact nonperturbative quantum symmetries. The selection rule that survives the electroweak anomaly is $B-L$, until higher-dimensional operators such as the Weinberg operator are added.
:::

## Higher-dimensional operators break the accident

The accidental symmetries are properties of the dimension-four operator list. They are not sacred once we allow higher-dimensional operators.

The leading lepton-number-violating operator built only from Standard Model fields is the Weinberg operator,

$$
\mathcal O_5
=
\frac{C_{\alpha\beta}}{\Lambda}
\left(L_\alpha H\right)
\left(L_\beta H\right)+\text{h.c.},
$$

with gauge indices contracted appropriately. It has

$$
\Delta L=2,
\qquad
\Delta B=0.
$$

After electroweak symmetry breaking it gives Majorana neutrino masses of order

$$
m_\nu\sim \frac{v^2}{\Lambda}.
$$

This operator breaks total lepton number and $B-L$. That is why Majorana neutrino masses are qualitatively different from charged-fermion Dirac masses.

Baryon-number violation first appears through dimension-six four-fermion operators. Typical schematic classes include

$$
Q_LQ_LQ_LL_L,
\qquad
u_Ru_Rd_Re_R,
$$

where charge conjugation matrices and color, weak, Lorentz, and generation contractions are suppressed. The exact independent SMEFT basis is a later topic. The dimensional reason is already visible: a proton-decay operator needs three quark fields and one lepton field. Four fermions have total canonical dimension

$$
4\times\frac32=6.
$$

Thus proton decay is absent at dimension four but allowed at dimension six by Standard Model gauge invariance.

A typical baryon- and lepton-number violating EFT term has the form

$$
\Delta\mathcal L
\sim
\frac{1}{\Lambda^2}
qqql+\text{h.c.},
$$

with

$$
\Delta B=\Delta L=1,
\qquad
\Delta(B-L)=0.
$$

The long observed proton lifetime therefore constrains the scale suppressing these operators to be very high, unless their coefficients are tiny or protected by additional symmetries.

## A cleaner operator table

Here is the conceptual table to remember.

| Operator level | Example | Symmetry consequence |
|---|---|---|
| Dimension $\le4$ | Standard Model gauge, Higgs, Yukawa terms | Conserves $B$ and $L$ classically. |
| Electroweak anomaly | Sphaleron or instanton transition | Violates $B+L$, preserves $B-L$. |
| Dimension $5$ | Weinberg operator $(LH)(LH)/\Lambda$ | Violates $L$ by two units and breaks $B-L$. |
| Dimension $6$ | Proton-decay operators $qqql/\Lambda^2$ | Can violate $B$ and $L$, often preserving $B-L$. |
| Higher dimensions | Many SMEFT operators | Break or preserve accidental symmetries depending on quantum numbers. |

The operator dimension matters because an effective field theory organizes corrections by powers of $E/\Lambda$. Accidental symmetries are often excellent approximations because their first violations occur only at high operator dimension.

## Custodial symmetry is a different kind of accident

The Higgs potential by itself has a larger global symmetry than the full Standard Model makes obvious. Writing the Higgs doublet as a $2\times2$ matrix

$$
\Sigma=(\widetilde H, H),
\qquad
\widetilde H=i\sigma^2H^*,
$$

the scalar potential depends only on

$$
H^\dagger H=\frac12\operatorname{tr}(\Sigma^\dagger\Sigma).
$$

In the limit $g'\to0$ and with suitably symmetric Yukawa couplings, the Higgs sector has an approximate

$$
SU(2)_L\times SU(2)_R
$$

global symmetry broken to diagonal custodial

$$
SU(2)_V.
$$

This approximate custodial symmetry helps explain the tree-level relation

$$
\rho
=
\frac{M_W^2}{M_Z^2\cos^2\theta_W}=1.
$$

But custodial symmetry is not the same type of accidental symmetry as baryon number. It is not an exact symmetry of the full Standard Model: hypercharge and the unequal up- and down-type Yukawa matrices break it. It is nevertheless an important approximate organizing principle for electroweak precision physics.

## Common mistakes

**Saying baryon number is a gauge symmetry.** In the minimal Standard Model, baryon number is a global accidental symmetry of the renormalizable Lagrangian. Gauging it requires extra consistency checks and usually extra fields.

**Forgetting the anomaly.** $B$ and $L$ are conserved perturbatively at dimension four, but $B+L$ is violated by electroweak topological processes. The anomaly-free combination with respect to the Standard Model gauge fields is $B-L$.

**Treating lepton family number as exact in nature.** The minimal massless-neutrino Standard Model has separate charged-lepton family numbers. Neutrino masses and PMNS mixing remove that exact symmetry.

**Thinking accidental means approximate by definition.** Accidental symmetries can be exact inside a specified truncated theory. They become approximate when the theory is viewed as an EFT with additional higher-dimensional operators.

**Confusing custodial symmetry with baryon and lepton number.** Custodial symmetry is an approximate global symmetry of the Higgs/electroweak sector in special limits. Baryon and lepton number are automatic selection rules of the dimension-four operator list.

## Exercises

### Exercise 1: Yukawa terms preserve baryon number

Check explicitly that the up- and down-type quark Yukawa terms preserve baryon number.

<details><summary><strong>Solution</strong></summary>

The down-type term is

$$
\bar Q_L H Y_d d_R.
$$

Since $B(Q_L)=B(d_R)=1/3$ and $B(H)=0$,

$$
B(\bar Q_L H d_R)=-\frac13+0+\frac13=0.
$$

The up-type term is

$$
\bar Q_L\widetilde H Y_u u_R,
$$

and similarly

$$
B(\bar Q_L\widetilde H u_R)=-\frac13+0+\frac13=0.
$$

Therefore the quark Yukawa interactions preserve total baryon number.

</details>

### Exercise 2: Why proton decay first appears at dimension six

Use canonical dimensions to explain why a schematic proton-decay operator made from three quark fields and one lepton field is not renormalizable.

<details><summary><strong>Solution</strong></summary>

A four-dimensional fermion field has canonical dimension $3/2$. A local operator made from three quarks and one lepton has dimension

$$
4\times\frac32=6.
$$

Therefore its coefficient has mass dimension $-2$ and appears as

$$
\Delta\mathcal L\sim\frac{1}{\Lambda^2}qqql.
$$

It is a dimension-six EFT correction, not a renormalizable dimension-four Standard Model interaction.

</details>

### Exercise 3: The Weinberg operator violates lepton number

Assume $L(L)=1$ and $L(H)=0$. What lepton number is carried by $(LH)(LH)$?

<details><summary><strong>Solution</strong></summary>

Each factor $LH$ has lepton number

$$
L(LH)=1+0=1.
$$

Therefore

$$
L\big((LH)(LH)\big)=2.
$$

The Weinberg operator changes lepton number by two units. After electroweak symmetry breaking it gives a Majorana neutrino mass term, which also violates lepton number by two units.

</details>

### Exercise 4: Electroweak anomaly and $B-L$

If an electroweak topological transition has $\Delta B=\Delta L=N_g$, show that $B-L$ is preserved and $B+L$ is violated.

<details><summary><strong>Solution</strong></summary>

We compute

$$
\Delta(B-L)=\Delta B-\Delta L=N_g-N_g=0,
$$

but

$$
\Delta(B+L)=\Delta B+\Delta L=2N_g.
$$

For $N_g=3$, this gives $\Delta(B+L)=6$ for one unit of topological charge.

</details>

## Relations to other pages

- [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/) gives the dimension-four operator list whose accidental symmetries are being analyzed.
- [Parameter Counting](/gauge-theories-standard-model/standard-model/parameter-counting/) explains how flavor rotations and Yukawa matrices reduce the raw couplings to physical parameters.
- [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) explains the leading lepton-number-violating operator.
- [Baryon and Lepton Number Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/baryon-and-lepton-number-anomalies/) gives the anomaly calculation behind $B+L$ violation.
- [Mass Spectrum and Couplings](/gauge-theories-standard-model/standard-model/mass-spectrum-and-couplings/) explains the mass-basis theory in which many accidental selection rules are used phenomenologically.

## Research status

The accidental-symmetry structure of the minimal renormalizable Standard Model is settled. What remains open is what breaks these symmetries in the ultraviolet, if anything. Neutrino masses already require lepton-number physics beyond the minimal renormalizable theory. Proton decay has not been observed, which severely constrains baryon-number violation. The baryon asymmetry of the universe suggests that some baryon- or lepton-number violating dynamics, together with CP violation and departure from equilibrium, occurred in the early universe.

## Where to go next

Continue to [Mass Spectrum and Couplings](/gauge-theories-standard-model/standard-model/mass-spectrum-and-couplings/). Accidental symmetries tell us which processes are absent or suppressed; the mass spectrum tells us which particles and interactions actually propagate after electroweak symmetry breaking.

After that, go to [Limitations of the Standard Model](/gauge-theories-standard-model/standard-model/limitations-of-the-standard-model/) and then to the Anomalies and Consistency chapter.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the chiral gauge theory, anomaly, Standard Model, and neutrino-mass sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction, CP-violation, anomaly, and precision-test chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the chapter on the Standard Model as an effective theory.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and global-symmetry structure of the Standard Model.
- Coleman, *Aspects of Symmetry*, especially the lectures on symmetries, currents, anomalies, and hidden symmetry.

## Version history

- **2026-06-19:** Initial page explaining baryon number, lepton number, anomaly qualifications, higher-dimensional violations, and custodial-symmetry caveats.
