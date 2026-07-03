---
title: "Standard Model Effective Field Theory"
description: "SMEFT as the gauge-invariant effective field theory of Standard Model fields: operator expansion, Wilson coefficients, electroweak symmetry, flavor, matching, running, observables, and validity." 
sidebar:
  label: "Standard Model Effective Field Theory"
  order: 80
level: Advanced
status: "Polished draft"
source: "Weinberg 1979; Buchmüller and Wyler 1986; Grzadkowski et al. 2010; Jenkins, Manohar, and Trott 2013–2014; Brivio and Trott 2019; Burgess 2020, ch. 9."
topics:
  - Standard Model effective field theory
  - SMEFT
  - Wilson coefficients
  - operator bases
  - electroweak symmetry
  - matching and running
canonicalTopics:
  - smeft
  - standard-model-effective-field-theory
  - wilson-coefficients
researchStatus:
  established:
    - "SMEFT is the standard EFT for parametrizing heavy new physics that preserves the Standard Model gauge group and has no light non-Standard-Model degrees of freedom."
  active:
    - "Global SMEFT fits, flavor assumptions, dimension-eight effects, nonlinear electroweak EFT comparisons, renormalization beyond leading order, and collider-observable truncation choices remain active research areas."
---

## Summary

**Standard Model effective field theory**, or **SMEFT**, is the effective field theory obtained by adding all local operators built from Standard Model fields and respecting the Standard Model gauge symmetry

$$
SU(3)_c\times SU(2)_L\times U(1)_Y.
$$

It describes the low-energy effects of heavy new degrees of freedom at a scale $\Lambda$ when those degrees of freedom are not produced directly and when the Higgs belongs to the usual electroweak doublet $H$. The Lagrangian is organized as

$$
\mathcal L_{\mathrm{SMEFT}}
=\mathcal L_{\mathrm{SM}}
+\sum_i \frac{C_i^{(5)}}{\Lambda}\mathcal O_i^{(5)}
+\sum_i \frac{C_i^{(6)}}{\Lambda^2}\mathcal O_i^{(6)}
+\sum_i \frac{C_i^{(7)}}{\Lambda^3}\mathcal O_i^{(7)}
+\cdots .
$$

The Wilson coefficients $C_i^{(d)}$ encode short-distance physics. The operators $\mathcal O_i^{(d)}$ encode the allowed low-energy effects. The expansion parameter is not simply "new physics is weak." It is

$$
\frac{E}{\Lambda}\ll 1,
$$

where $E$ is the characteristic energy or momentum transfer of the process.

The first operator beyond the Standard Model that violates lepton number is the dimension-five Weinberg operator,

$$
\mathcal O_5=(L^T C i\sigma^2 H)(H^T i\sigma^2 L),
$$

which gives Majorana neutrino masses after electroweak symmetry breaking. Most precision collider and electroweak applications focus on dimension-six operators, schematically

$$
\mathcal L_{\mathrm{SMEFT}}
=\mathcal L_{\mathrm{SM}}
+\frac{1}{\Lambda^2}\sum_i C_i\mathcal O_i
+O(\Lambda^{-4}),
$$

with the dimension-five term treated separately when neutrino mass is relevant.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![SMEFT map from heavy new physics through gauge-invariant operator tower, matching, anomalous-dimension running, electroweak symmetry breaking, and low-energy observables](/figures/renormalization-rg-eft/smeft-operator-tower.svg)

<figcaption>

SMEFT separates heavy short-distance physics from low-energy observables. Matching determines gauge-invariant Wilson coefficients at a high scale; RG evolution moves them to the relevant scale; electroweak symmetry breaking translates them into corrections to masses, couplings, and scattering amplitudes.

</figcaption>
</figure>

:::note[The punchline]
SMEFT is not a list of arbitrary anomalous couplings. It is the local, gauge-invariant, systematically improvable expansion of the Standard Model in powers of $1/\Lambda$.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/), and [Gauge Theories and RG](/renormalization-rg-eft/gauge-theories-and-rg/).

This page assumes the Standard Model field content and the unbroken gauge group $SU(3)_c\times SU(2)_L\times U(1)_Y$. It uses the mostly-minus convention and natural units. The Higgs doublet has hypercharge $+1/2$.

## Core idea

The Standard Model is the most general renormalizable QFT with its observed gauge symmetries and field content. SMEFT asks a sharper question:

> What is the most general local QFT built from the same light fields and symmetries, when heavier particles have been integrated out?

The answer is an infinite tower of higher-dimension operators. This tower is not a failure of predictivity, because at any fixed order in $E/\Lambda$ only finitely many operators contribute to a given accuracy. SMEFT is therefore an organized expansion around the Standard Model, not a replacement for it.

The logic is

$$
\text{heavy physics at }\Lambda
\longrightarrow
\text{matching coefficients }C_i(\Lambda)
\longrightarrow
\text{running }C_i(\mu)
\longrightarrow
\text{observable deviations}.
$$

The important phrase is **gauge invariant before electroweak symmetry breaking**. SMEFT operators are written using $H$, $L$, $Q$, $u_R$, $d_R$, $e_R$, gauge-field strengths, and covariant derivatives while $SU(2)_L\times U(1)_Y$ is still linearly realized. After $H$ gets a vacuum expectation value, those operators become correlated shifts in many low-energy couplings.

## Field content and dimensions

The Standard Model matter fields are

| Field | Gauge representation | Dimension |
|---|---|---:|
| $Q$ | left-handed quark doublet | $3/2$ |
| $u_R,d_R$ | right-handed quark singlets | $3/2$ |
| $L$ | left-handed lepton doublet | $3/2$ |
| $e_R$ | right-handed charged-lepton singlet | $3/2$ |
| $H$ | Higgs doublet | $1$ |
| $G_{\mu\nu},W_{\mu\nu},B_{\mu\nu}$ | gauge-field strengths | $2$ |
| $D_\mu$ | covariant derivative | $1$ |

Here "representation" is described in words because the full color, weak-isospin, hypercharge, and flavor indices make compact tables ugly fast. A serious SMEFT calculation must restore those indices.

The operator dimension fixes its suppression. A local operator $\mathcal O^{(d)}$ with mass dimension $d$ appears as

$$
\Delta\mathcal L^{(d)}
=\sum_i \frac{C_i^{(d)}}{\Lambda^{d-4}}\mathcal O_i^{(d)}.
$$

The coefficients $C_i^{(d)}$ are dimensionless in this normalization. Some authors instead absorb powers of $\Lambda$ into coefficients. When comparing papers, first identify the normalization.

## Dimension five: the Weinberg operator

With the Standard Model field content and baryon number preserved, the unique lepton-number-violating dimension-five structure is the Weinberg operator. A convenient schematic form is

$$
\Delta\mathcal L_5
=\frac{C_5^{ij}}{\Lambda}
(L_i^T C i\sigma^2 H)(H^T i\sigma^2 L_j)+\text{h.c.},
$$

where $i,j$ are flavor indices and $C$ is the Lorentz charge-conjugation matrix. After electroweak symmetry breaking,

$$
H\longrightarrow \frac{1}{\sqrt2}\begin{pmatrix}0\\ v+h\end{pmatrix},
$$

the operator gives a Majorana mass matrix

$$
(m_\nu)_{ij}\sim \frac{v^2}{\Lambda}C_5^{ij}.
$$

This is the cleanest example of SMEFT logic. A high scale can leave a small low-energy imprint because the operator is suppressed by $1/\Lambda$ but enhanced by the Higgs vacuum expectation value after symmetry breaking.

## Dimension six: correlated deviations

Dimension-six SMEFT operators are often grouped by structure:

| Type | Schematic form | What it affects |
|---|---|---|
| Pure Higgs | $H^6$, $H^4D^2$ | Higgs potential, Higgs couplings, electroweak inputs |
| Gauge field strengths | $X^3$, $H^2X^2$ | triple-gauge couplings, Higgs-to-gauge couplings |
| Fermion-Higgs | $\psi^2H^3$ | Yukawa interactions and flavor structure |
| Fermion-current | $\psi^2H^2D$ | gauge-fermion couplings and electroweak precision tests |
| Dipoles | $\psi^2HX$ | magnetic moments, radiative decays, flavor violation |
| Four-fermion | $\psi^4$ | contact interactions, flavor, weak decays, collider tails |

Here $X$ stands for a gauge-field strength and $\psi$ for a fermion. These schematic categories are not a basis. They are a map of the territory.

A representative example is

$$
\mathcal O_{HWB}=H^\dagger\sigma^I H\,W^I_{\mu\nu}B^{\mu\nu}.
$$

After electroweak symmetry breaking, this operator contributes to neutral gauge-boson kinetic mixing and therefore affects electroweak precision observables. Another example is

$$
\mathcal O_{uG}=\bar Q\sigma^{\mu\nu}T^A u_R\,\widetilde H\,G^A_{\mu\nu},
$$

which is a quark chromomagnetic dipole operator. Its physical effects are very different from $\mathcal O_{HWB}$, but both are part of the same gauge-invariant expansion.

## Operator bases and redundancies

SMEFT has many operator bases. The most widely used dimension-six basis is the **Warsaw basis**, but other bases are useful for different questions. A basis is a choice of independent representatives after removing redundancies from:

- integration by parts;
- equations of motion;
- algebraic identities such as Fierz identities;
- Bianchi identities;
- field redefinitions;
- flavor and Hermiticity relations.

The underlying physics is independent of the basis. If

$$
\mathcal O_i\longrightarrow \mathcal O'_a=R_a{}^i\mathcal O_i,
$$

then Wilson coefficients transform dually,

$$
C'_a=(R^{-1})^i{}_a C_i,
$$

so that

$$
\sum_i C_i\mathcal O_i=\sum_a C'_a\mathcal O'_a.
$$

This equality is schematic because singular, redundant, or flavor-dependent transformations require care. The moral is robust: bases are coordinates, not observables.

:::tip[Do not worship a basis]
The Warsaw basis is a superb common language. It is not the physics. Observables, symmetries, matching conditions, and RG-invariant conclusions are the physics.
:::

## Matching heavy physics onto SMEFT

Suppose a heavy particle of mass $M\sim\Lambda$ couples to Standard Model fields. At energies $E\ll M$, its propagator can be expanded in powers of momenta over $M$. The result is a tower of local operators.

For a schematic heavy vector $X_\mu$ coupled to a Standard Model current $J^\mu$,

$$
\mathcal L\supset \frac12M^2X_\mu X^\mu+g_X X_\mu J^\mu.
$$

Solving the classical equation of motion gives, at leading order,

$$
X_\mu\simeq -\frac{g_X}{M^2}J_\mu,
$$

and therefore

$$
\Delta\mathcal L_{\mathrm{eff}}
\sim -\frac{g_X^2}{2M^2}J_\mu J^\mu.
$$

If $J^\mu$ is made from Standard Model fields and respects the gauge symmetry, this is a dimension-six SMEFT operator. Loop-level matching works similarly, but one equates amplitudes or correlators in the full theory and SMEFT at the same order, subtracting EFT loops to avoid double counting.

## Running and mixing

Wilson coefficients depend on the renormalization scale:

$$
\mu\frac{d C_i}{d\mu}=\gamma_i{}^j C_j.
$$

The anomalous-dimension matrix $\gamma_i{}^j$ is generally not diagonal. A coefficient generated at the matching scale can therefore generate other coefficients at a lower scale. This is not optional bookkeeping: it is how large logarithms such as

$$
\log\frac{\Lambda}{m_Z}
$$

are resummed.

For a single coefficient with approximately constant anomalous dimension,

$$
C(\mu)\simeq C(\Lambda)
\left[1+\gamma\log\frac{\mu}{\Lambda}+\cdots\right].
$$

For many operators, the solution is a matrix evolution problem. This is why SMEFT requires careful operator bases and flavor conventions.

## Electroweak symmetry breaking and input schemes

SMEFT is written in the unbroken electroweak phase, but many observables are measured after electroweak symmetry breaking. This introduces a subtle but crucial step. Operators can shift the relations among Lagrangian parameters and measured inputs such as

$$
\alpha_{\mathrm{em}},\qquad G_F,
\qquad m_Z,
\qquad m_W,
\qquad m_h.
$$

A prediction must specify an **input scheme**. For example, one may take $\{\alpha_{\mathrm{em}},G_F,m_Z\}$ as inputs and predict shifts in other observables, or choose a different set. The Wilson coefficients then enter both directly through interaction vertices and indirectly through parameter redefinitions.

This is one reason why "turning on one anomalous coupling" can be misleading. Gauge invariance and input-parameter shifts correlate many apparent deviations.

## Flavor structure

SMEFT flavor is a blessing and a monster wearing the same hat. With three generations, many operators carry flavor indices. A four-fermion operator is not just one operator; it may represent a large tensor of coefficients.

Common flavor assumptions include:

| Assumption | Meaning | Risk |
|---|---|---|
| Flavor universal | coefficients are generation independent | may miss flavor-specific new physics |
| Minimal flavor violation | flavor breaking aligned with SM Yukawas | elegant but model-assumptive |
| Third-generation focus | largest effects near top, bottom, tau | useful at colliders but incomplete |
| General flavor | no simplifying assumption | many coefficients and strong constraints |

A SMEFT statement without flavor assumptions is usually incomplete. The right assumption depends on the question.

## Validity and truncation

At dimension six, an observable may be expanded as

$$
\mathcal O_{\mathrm{obs}}
=\mathcal O_{\mathrm{SM}}
+\frac{1}{\Lambda^2}\sum_i C_i\mathcal O_i^{\mathrm{int}}
+\frac{1}{\Lambda^4}\left(\sum_{i,j}C_iC_j\mathcal O_{ij}^{\mathrm{quad}}
+\sum_k C_k^{(8)}\mathcal O_k^{(8),\mathrm{int}}\right)
+\cdots .
$$

The first correction is usually the interference between the Standard Model amplitude and a dimension-six amplitude. The $1/\Lambda^4$ terms include both squared dimension-six contributions and interference from dimension-eight operators. Keeping the former while dropping the latter can be numerically useful, but it is not a fully systematic dimension-six truncation unless justified.

A trustworthy SMEFT analysis should state:

| Choice | Why it matters |
|---|---|
| Maximum operator dimension | fixes the formal truncation order |
| Energy range | controls the expansion in $E/\Lambda$ |
| Flavor assumptions | control coefficient counting and correlations |
| Input scheme | controls parameter shifts |
| Basis | controls coefficient names, not physics |
| Linear versus quadratic terms | controls formal power counting |
| RG order | controls logarithmic accuracy |

## SMEFT versus HEFT

SMEFT assumes the Higgs is part of a linearly transforming $SU(2)_L$ doublet. A more general low-energy description, often called **HEFT** or electroweak chiral EFT, treats the physical Higgs as an electroweak singlet and realizes electroweak symmetry nonlinearly.

The distinction is physical:

| Framework | Higgs organization | Best suited for |
|---|---|---|
| SMEFT | Higgs in a linear doublet $H$ | heavy new physics with ordinary Higgs-doublet structure |
| HEFT | Higgs singlet plus Goldstone matrix | strongly coupled or nonlinear electroweak sectors |

SMEFT is usually the right default for high-scale decoupling new physics. HEFT is not "SMEFT done badly"; it is a different expansion with different assumptions.

## Common pitfalls

**Treating SMEFT coefficients as independent anomalous couplings after electroweak symmetry breaking.** Gauge invariance relates many deviations that look independent in a broken-phase parametrization.

**Forgetting input-parameter shifts.** Operators can change how $g$, $g'$, $v$, and Yukawa couplings are inferred from measured quantities.

**Ignoring flavor.** A coefficient label without flavor assumptions may hide dozens or hundreds of independent entries.

**Using SMEFT outside its energy range.** If events probe invariant masses comparable to $\Lambda$, the local expansion is no longer controlled.

**Keeping squared dimension-six terms without discussing dimension-eight terms.** This may be useful, especially when interference is suppressed, but it is a truncation choice that needs to be stated.

**Confusing basis dependence with physics.** Wilson coefficients are coordinates. Observables are basis independent.

## Relations to other pages

SMEFT is the Standard Model application of [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), and [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/). It is closely related to [Fermi Theory](/renormalization-rg-eft/major-efts/fermi-theory/) as its electroweak ancestor, to [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) through anomalous-dimension matrices, and to [Naturalness and Power Counting](/renormalization-rg-eft/naturalness-power-counting/) through the interpretation of Higgs-sector corrections.

## Research status

SMEFT itself is established. What remains active is not the basic expansion, but its precision deployment: complete higher-order matching, global fits with correlations and flat directions, treatment of dimension-eight effects, flavor assumptions, positivity constraints, nonlinear EFT comparisons, basis translations, and the interface between collider observables and EFT truncation.

## Exercises

### Exercise 1: Dimension of the Weinberg operator

Using $[L]=3/2$ and $[H]=1$, show that $(LH)(LH)$ has dimension five and therefore appears with a coefficient of dimension $-1$.

<details><summary><strong>Solution</strong></summary>

The operator contains two lepton doublets and two Higgs doublets. Its engineering dimension is

$$
2[L]+2[H]=2\cdot\frac32+2\cdot1=3+2=5.
$$

Since the Lagrangian density has dimension four in four spacetime dimensions, the coefficient has dimension

$$
4-5=-1.
$$

It is therefore naturally written as $C_5/\Lambda$.

</details>

### Exercise 2: Why dimension six gives contact interactions

A heavy vector boson of mass $M$ couples to a conserved current $J^\mu$ through $g_X X_\mu J^\mu$. If $[J^\mu]=3$, show that the leading low-energy operator generated by tree-level exchange is dimension six.

<details><summary><strong>Solution</strong></summary>

At energies much smaller than $M$, the propagator reduces to a local factor proportional to $1/M^2$. The induced operator is schematically

$$
\Delta\mathcal L\sim \frac{g_X^2}{M^2}J_\mu J^\mu.
$$

Since $[J^\mu]=3$,

$$
[J_\mu J^\mu]=6.
$$

The coefficient must have dimension $4-6=-2$, which is provided by $1/M^2$. Thus the induced operator is dimension six.

</details>

### Exercise 3: Basis-invariant amplitude

Suppose two operators are related by an invertible basis change $\mathcal O'_a=R_a{}^i\mathcal O_i$. Find the coefficient transformation that keeps $\sum_i C_i\mathcal O_i$ unchanged.

<details><summary><strong>Solution</strong></summary>

We require

$$
\sum_i C_i\mathcal O_i=\sum_a C'_a\mathcal O'_a
=\sum_{a,i}C'_a R_a{}^i\mathcal O_i.
$$

Therefore

$$
C_i=\sum_a C'_a R_a{}^i.
$$

In matrix notation, if $\mathcal O'=R\mathcal O$, then

$$
C'=C R^{-1},
$$

or with indices as written above,

$$
C'_a=(R^{-1})^i{}_a C_i.
$$

The coefficient vector transforms dually to the operator vector.

</details>

## References

- Steven Weinberg, "Baryon- and Lepton-Nonconserving Processes," for the original dimension-five neutrino-mass operator logic.
- W. Buchmüller and D. Wyler, for an early systematic Standard Model operator analysis.
- B. Grzadkowski, M. Iskrzyński, M. Misiak, and J. Rosiek, for the Warsaw basis of dimension-six operators.
- E. E. Jenkins, A. V. Manohar, and M. Trott, for anomalous dimensions and SMEFT RG evolution.
- A. Brivio and M. Trott, for a modern SMEFT review.
- C. P. Burgess, *Introduction to Effective Field Theory*, for EFT logic, matching, and the Standard Model as an EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for Standard Model conventions, renormalization, EFT, and phenomenological examples.

## Version history

- 2026-06-19: First polished draft. Added SMEFT operator expansion, basis logic, matching, running, electroweak symmetry breaking, validity caveats, exercises, and figure.
