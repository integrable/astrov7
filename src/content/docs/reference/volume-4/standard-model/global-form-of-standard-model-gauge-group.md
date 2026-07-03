---
title: "Global Form of the Standard Model Gauge Group"
description: "Explains the quotient structure of the Standard Model gauge group, the Z6 identification, representation selection rules, and what global form changes physically."
sidebar:
  label: "Global Form of the Standard Model Gauge Group"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard Model gauge-group material in Srednicki §§87–89 and Schwartz Chs. 29–30; global-form and line-operator perspective from modern gauge-theory literature."
topics:
  - Standard Model global form
  - Z6 quotient
  - line operators
  - magnetic charges
  - representation selection rules
canonicalTopics:
  - standard-model-global-form
  - standard-model-z6-quotient
  - standard-model-line-operators
  - hypercharge-quantization
researchStatus:
  established:
    - "The local Standard Model gauge algebra is fixed by perturbative interactions, while the quotient by a subgroup of the common center is additional global gauge-theory data."
  active:
    - "Different global forms have the same ordinary perturbative vertices but differ in allowed line operators, bundles, magnetic sectors, and possible ultraviolet embeddings."
---

## Summary

The Standard Model gauge algebra is

$$
\mathfrak g_{\rm SM}
=
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak u(1)_Y.
$$

That algebra does **not** uniquely determine the global gauge group. A first-pass notation is

$$
\widetilde G
=
SU(3)_c\times SU(2)_L\times U(1)_Y,
$$

but the minimal Standard Model fields are all blind to a diagonal order-six subgroup of the center. Thus a natural global form is

$$
G_{\rm SM}
=
\frac{SU(3)_c\times SU(2)_L\times U(1)_Y}{\mathbb Z_6}.
$$

More generally one can consider

$$
G_\Gamma
=
\frac{SU(3)_c\times SU(2)_L\times U(1)_Y}{\Gamma},
\qquad
\Gamma\subseteq\mathbb Z_6.
$$

All these choices have the same local Lie algebra. They give the same textbook covariant derivative and the same ordinary perturbative vertices for the known fields. They differ in global questions: which Wilson lines are genuine, which magnetic charges are allowed, which bundles exist on nontrivial spacetime manifolds, and which ultraviolet completions are naturally compatible.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Global form of the Standard Model gauge group](/figures/gauge-theories-standard-model/standard-model-global-form-map.svg)

<figcaption>

The local Standard Model gauge algebra fixes infinitesimal transformations. The global form further divides the product group by a diagonal subgroup of the centers. The quotient is invisible to ordinary local vertices but visible to representations, bundles, line operators, and magnetic sectors.

</figcaption>
</figure>

The conceptual lesson is simple and slightly treacherous: a gauge theory is not fully specified by its Lie algebra.

## Prerequisites

You should know the [Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/standard-model-gauge-group/), [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/), [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), and [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/). The page also uses the idea of Wilson and ’t Hooft lines from [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/) and [’t Hooft Loops](/gauge-theories-standard-model/wilson-loops-confinement/thooft-loops/), but only at a structural level.

We use

$$
Q=T^3+Y
$$

and define the integral hypercharge

$$
\mathsf y=6Y.
$$

The normalization $\mathsf y=6Y$ is convenient because every minimal Standard Model multiplet has integer $\mathsf y$.

## Local algebra versus global group

The Lie algebra tells us the infinitesimal generators and local gauge bosons:

$$
G_\mu^A,
\qquad
W_\mu^I,
\qquad
B_\mu.
$$

It is enough to write the local covariant derivative

$$
D_\mu
=
\partial_\mu
+i g_sG_\mu^AT^A
+i gW_\mu^It^I
+i g'YB_\mu.
$$

But the global group tells us which finite transformations are identified. Two groups can have the same Lie algebra but different centers and different representation categories. The classic baby example is

$$
SU(2)
\quad\text{versus}\quad
SO(3)=SU(2)/\mathbb Z_2.
$$

They have the same Lie algebra $\mathfrak{su}(2)$, but $SU(2)$ allows doublet representations while $SO(3)$ does not. Perturbation theory around the identity sees the same gauge bosons; global topology sees a different theory.

The Standard Model has the same kind of issue, but with a diagonal subgroup tying together color triality, weak isospin parity, and hypercharge.

## Centers and the diagonal generator

The center of $SU(3)$ is

$$
Z(SU(3))=\{1,\omega_3,\omega_3^2\},
\qquad
\omega_3=e^{2\pi i/3},
$$

and the center of $SU(2)$ is

$$
Z(SU(2))=\{1,-1\}.
$$

With integral hypercharge $\mathsf y=6Y$, let the $U(1)$ element $e^{i\theta}$ act on a field of charge $\mathsf y$ by

$$
\Psi\mapsto e^{i\mathsf y\theta}\Psi.
$$

Now consider the central element

$$
\gamma
=
\left(\omega_3\mathbf1_3,\,-\mathbf1_2,\,e^{i\pi/3}\right)
\in
SU(3)_c\times SU(2)_L\times U(1)_Y.
$$

It has order six. A field in a color representation of triality $t\in\mathbb Z_3$, an $SU(2)$ representation with center parity $s\in\mathbb Z_2$, and integral hypercharge $\mathsf y$ transforms under $\gamma$ by

$$
\exp\left[\frac{2\pi i}{3}t\right]
\exp[i\pi s]
\exp\left[\frac{i\pi}{3}\mathsf y\right]
=
\exp\left[\frac{i\pi}{3}(\mathsf y+2t+3s)\right].
$$

Thus $\gamma$ acts trivially exactly when

$$
\mathsf y+2t+3s\equiv0\pmod 6.
$$

This is the Standard Model quotient rule in a compact form.

Here $t=1$ for a color fundamental $\mathbf3$, $t=-1$ for an antifundamental $\bar{\mathbf3}$, and $t=0$ for color singlets and adjoints. Similarly, $s=1$ for half-integer weak-isospin representations such as doublets, and $s=0$ for integer weak-isospin representations such as singlets and adjoints.

## Check on the minimal fields

The minimal Standard Model multiplets obey the quotient rule. In particle notation, one generation has

| Field | Representation | $\mathsf y=6Y$ | $(t,s)$ | $\mathsf y+2t+3s$ |
|---|---:|---:|---:|---:|
| $Q_L$ | $(\mathbf3,\mathbf2)_{1/6}$ | $1$ | $(1,1)$ | $6$ |
| $u_R$ | $(\mathbf3,\mathbf1)_{2/3}$ | $4$ | $(1,0)$ | $6$ |
| $d_R$ | $(\mathbf3,\mathbf1)_{-1/3}$ | $-2$ | $(1,0)$ | $0$ |
| $L_L$ | $(\mathbf1,\mathbf2)_{-1/2}$ | $-3$ | $(0,1)$ | $0$ |
| $e_R$ | $(\mathbf1,\mathbf1)_{-1}$ | $-6$ | $(0,0)$ | $-6$ |
| $H$ | $(\mathbf1,\mathbf2)_{1/2}$ | $3$ | $(0,1)$ | $6$ |

Each entry is divisible by six. Therefore the element $\gamma$ acts trivially on every minimal Standard Model matter and Higgs multiplet. The gauge bosons also pass the test: they are in adjoint representations and have $\mathsf y=0$.

A sterile right-handed neutrino, if added as

$$
\nu_R\sim(\mathbf1,\mathbf1)_0,
$$

also passes the test. It is completely neutral under the Standard Model gauge group, so it does not distinguish the quotient.

## Subquotients

The cyclic subgroup generated by $\gamma$ has subgroups

$$
\mathbb Z_2=\langle\gamma^3\rangle,
\qquad
\mathbb Z_3=\langle\gamma^2\rangle,
\qquad
\mathbb Z_6=\langle\gamma\rangle.
$$

The corresponding selection rules are weaker for the subgroups:

| Quotient | Generator | Representation constraint |
|---|---|---|
| $\mathbb Z_2$ | $\gamma^3=(1,-1,e^{i\pi})$ | $\mathsf y+s\equiv0\pmod2$ |
| $\mathbb Z_3$ | $\gamma^2=(\omega_3^2,1,e^{2\pi i/3})$ | $\mathsf y+2t\equiv0\pmod3$ |
| $\mathbb Z_6$ | $\gamma=(\omega_3,-1,e^{i\pi/3})$ | $\mathsf y+2t+3s\equiv0\pmod6$ |

The minimal Standard Model fields satisfy all three because they satisfy the strongest rule. If one adds new matter, however, the choice of global form becomes a real restriction. For example, an $SU(2)_L$ doublet with $Y=0$ would have $\mathsf y=0$ and $s=1$, so it would not be a representation of the $\mathbb Z_2$ or $\mathbb Z_6$ quotient.

This is one reason the sentence “add a new multiplet” is not quite complete. One must also say which global gauge group the multiplet is supposed to represent.

## Relation to SU(5)

The $\mathbb Z_6$ quotient appears naturally in the Georgi–Glashow $SU(5)$ embedding. Inside $SU(5)$, the subgroup preserving a splitting

$$
\mathbb C^5=\mathbb C^3\oplus\mathbb C^2
$$

is

$$
S(U(3)\times U(2))
=
\left\{(U_3,U_2)\in U(3)\times U(2):\det U_3\det U_2=1\right\}.
$$

This group is isomorphic to

$$
\frac{SU(3)\times SU(2)\times U(1)}{\mathbb Z_6}.
$$

The quotient is therefore not an arbitrary afterthought. It is exactly the global form selected by the simplest $SU(5)$ grand-unified embedding. Grand unification is not required for the quotient to make sense, but it gives an elegant reason to expect it.

## What the global form changes

The global form does not change the local gauge algebra or the ordinary Standard Model vertices. A local perturbative calculation of $e^+e^-\to\mu^+\mu^-$, a Higgs decay width, or a QCD beta function will not notice whether one wrote $\widetilde G$ or $\widetilde G/\mathbb Z_6$.

It can change the following.

**Allowed electric line operators.** Wilson lines are labelled by representations. A quotient removes Wilson lines whose representation does not descend to the quotient group.

**Allowed magnetic line operators.** ’t Hooft lines are labelled by magnetic charges in a dual lattice. Changing the electric lattice changes the compatible magnetic lattice.

**Bundles on nontrivial manifolds.** Gauge fields are connections on principal bundles. Distinct global forms allow different principal bundles, and on curved or topologically nontrivial manifolds these differences can be physically meaningful.

**Theta-angle periodicities.** Nontrivial bundle sectors can change instanton-number quantization and therefore the periodicities or identifications of theta angles.

**Ultraviolet embeddings.** A proposed grand unified theory, string compactification, or other ultraviolet completion may naturally realize one global form rather than another.

**Higher-form symmetry bookkeeping.** The center quotient is closely related to which line operators are genuine and which center charges can be screened by dynamical matter. This is not the same as saying the Standard Model has an unbroken pure-gauge center symmetry; the Higgs and quarks screen many center charges. But the language is the same language of extended operators.

## What the global form does not change

It is equally important not to oversell the quotient.

The quotient does not change the number of gauge bosons:

$$
8+3+1=12.
$$

It does not change the local covariant derivative, the Lie algebra, the hypercharge assignments of the known fields, or the tree-level Feynman rules.

It does not by itself explain why there are three generations, why the Yukawa matrices have their observed hierarchy, why neutrinos are light, why the electroweak scale is small compared with plausible ultraviolet scales, or why the QCD theta angle is tiny. Those are deeper structural questions treated elsewhere.

The quotient is not a magic wand. It is a boundary condition on what the words “the Standard Model gauge group” mean globally.

## A useful mental model

Think of the local algebra as specifying the tangent space to the gauge group at the identity. It tells you how to move infinitesimally. The global form tells you which far-away points are actually the same point.

For most perturbative calculations, you spend all your time near the identity. For line operators, monopoles, instantons, bundles, and global anomalies, you walk around the whole group. That is when the quotient stops being a footnote and starts collecting rent.

## Common pitfalls

**Saying “the gauge group is the Lie algebra.”** The Lie algebra is not the group. It is local data. The global group also includes identifications by the center.

**Assuming the product group is automatically wrong.** The product group is a valid way to describe local perturbation theory and can be a valid global choice if the spectrum and line operators are chosen accordingly. The point is that the choice must be specified.

**Assuming the $\mathbb Z_6$ quotient changes electric charges.** It does not change $Q=T^3+Y$ for the known fields. It explains a compatibility among their color, weak-isospin, and hypercharge assignments.

**Confusing center quotient with confinement.** Quotienting the gauge group and confining color are different statements. The first is global gauge-theory data; the second is infrared dynamics.

**Forgetting new matter.** A proposed new particle must be a representation of the chosen global group, not just of the Lie algebra. Some representations allowed by $SU(3)\times SU(2)\times U(1)$ do not descend to the $\mathbb Z_6$ quotient.

## Relations to other pages

- [Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/standard-model-gauge-group/) gives the local algebra, gauge bosons, hypercharge convention, and covariant derivative.
- [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/) lists the minimal fields that obey the $\mathbb Z_6$ quotient rule.
- [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/) explains the same issue in general Yang–Mills language.
- [Center Symmetry and Confinement](/gauge-theories-standard-model/wilson-loops-confinement/center-symmetry-and-confinement/) explains how center data acts on line operators and phases.
- [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/) explains a separate consistency condition: quantum gauge invariance of the chiral fermion measure.

## Research status

The quotient structure is standard global gauge-theory data. It is not speculative. What is more contextual is which global form Nature “chooses” once one specifies all possible line operators, nonperturbative sectors, and ultraviolet completion. Current ordinary perturbative particle-physics measurements determine the local algebra and representations of the observed fields, but they do not directly measure the full spectrum of line operators.

For most Standard Model calculations, writing $SU(3)_c\times SU(2)_L\times U(1)_Y$ is harmless shorthand. For topology-sensitive questions, the shorthand must be expanded.

## Exercises

### Exercise 1: Verify the diagonal generator

Show that

$$
\gamma=(\omega_3\mathbf1_3,-\mathbf1_2,e^{i\pi/3})
$$

acts trivially on $Q_L\sim(\mathbf3,\mathbf2)_{1/6}$.

<details>
<summary><strong>Solution</strong></summary>

For $Q_L$, the color factor is $\omega_3=e^{2\pi i/3}$, the weak-doublet factor is $-1=e^{i\pi}$, and the integral hypercharge is $\mathsf y=6Y=1$. The $U(1)$ factor is $e^{i\pi/3}$. Therefore

$$
\omega_3(-1)e^{i\pi/3}
=
e^{2\pi i/3}e^{i\pi}e^{i\pi/3}
=
e^{2\pi i}=1.
$$

Thus $Q_L$ is a representation of the $\mathbb Z_6$ quotient.

</details>

### Exercise 2: Derive the selection rule

A field has color triality $t$, weak center parity $s$, and integral hypercharge $\mathsf y$. Derive the condition for the field to descend to the $\mathbb Z_6$ quotient.

<details>
<summary><strong>Solution</strong></summary>

The diagonal generator acts by

$$
\exp\left[\frac{2\pi i}{3}t\right]
\exp[i\pi s]
\exp\left[\frac{i\pi}{3}\mathsf y\right]
=
\exp\left[\frac{i\pi}{3}(\mathsf y+2t+3s)\right].
$$

This is equal to $1$ exactly when

$$
\mathsf y+2t+3s\equiv0\pmod6.
$$

</details>

### Exercise 3: A forbidden doublet under the quotient

Consider a hypothetical color-singlet weak doublet $X\sim(\mathbf1,\mathbf2)_0$. Does it descend to the $\mathbb Z_6$ quotient?

<details>
<summary><strong>Solution</strong></summary>

For $X$, we have

$$
t=0,
\qquad
s=1,
\qquad
\mathsf y=0.
$$

The selection rule gives

$$
\mathsf y+2t+3s=3,
$$

which is not divisible by six. Therefore $X$ is a representation of the product group but not of the $\mathbb Z_6$ quotient. Adding such a field would force a different global-form choice.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the Standard Model gauge/Higgs, lepton, quark, and anomaly-adjacent sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the Yang–Mills, weak-interaction, and anomaly chapters.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and Standard Model gauge structure.

### Deeper references

- David Tong, “Line Operators in the Standard Model,” for the modern line-operator analysis of the possible Standard Model global forms.
- Reviews and lecture notes on generalized global symmetries for the relation between quotient choices, center data, and extended operators.
- Grand-unification references for the identification $S(U(3)\times U(2))\simeq(SU(3)\times SU(2)\times U(1))/\mathbb Z_6$.

## Version history

- **2026-06-19:** Initial page on the $\mathbb Z_6$ quotient, representation selection rules, line operators, and global-form caveats.
