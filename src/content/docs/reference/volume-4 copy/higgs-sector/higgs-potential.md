---
title: "Higgs Potential"
description: "Derives the minimal Standard Model Higgs potential, its vacuum condition, the tree-level Higgs mass, and the self-interaction coefficients."
sidebar:
  label: "Higgs Potential"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §87; Schwartz Chs. 28–29; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II electroweak chapters."
topics:
  - Higgs potential
  - electroweak vacuum
  - Higgs mass
  - scalar self-couplings
  - vacuum stability
canonicalTopics:
  - higgs-potential
  - electroweak-vacuum
  - higgs-mass-tree-level
  - higgs-self-couplings
researchStatus:
  established:
    - "At tree level in the minimal Standard Model, the renormalizable Higgs potential is V(H) = -μ² H†H + λ(H†H)², with v² = μ²/λ and m_h² = 2λv²."
  active:
    - "Loop-corrected effective potentials, vacuum stability, metastability, naturalness, and Higgs self-coupling measurements remain active interfaces between the Higgs potential and high-energy data."
---

## Summary

For one Standard Model Higgs doublet $H\sim(\mathbf 1,\mathbf 2)_{1/2}$, the most general renormalizable gauge-invariant potential is, up to an additive constant,

$$
V(H)=-\mu^2 H^\dagger H+\lambda(H^\dagger H)^2,
\qquad
\lambda>0.
$$

For $\mu^2>0$, the origin is unstable and the minima satisfy

$$
H^\dagger H=\frac{v^2}{2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

A neutral representative of the vacuum manifold is

$$
\langle H\rangle
=
\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v
\end{pmatrix}.
$$

In unitary gauge,

$$
H(x)=\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v+h(x)
\end{pmatrix},
$$

and the potential becomes, after dropping the constant vacuum energy,

$$
V(h)=\lambda v^2h^2+\lambda vh^3+\frac{\lambda}{4}h^4.
$$

Since a real scalar potential contains $\frac12m_h^2h^2$, the tree-level Higgs mass is

$$
m_h^2=2\lambda v^2=2\mu^2.
$$

Equivalently,

$$
V(h)=\frac12m_h^2h^2+\frac{m_h^2}{2v}h^3+\frac{m_h^2}{8v^2}h^4.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![Higgs potential and vacuum-structure map](/figures/gauge-theories-standard-model/higgs-potential-radial-profile.svg)

<figcaption>

The minimal potential is controlled by the invariant $x=H^\dagger H$. Minimization fixes $x=v^2/2$, and the unitary-gauge expansion separates the radial Higgs mode from the angular would-be Goldstone directions.

</figcaption>
</figure>

## Prerequisites

You should know [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/), especially the representation $H\sim(\mathbf 1,\mathbf 2)_{1/2}$ and the neutral vacuum direction. You should also know [Abelian Higgs Model](/gauge-theories-standard-model/higgs-sector/abelian-higgs-model/) and [Non-Abelian Higgs Mechanism](/gauge-theories-standard-model/higgs-sector/non-abelian-higgs-mechanism/) for the general logic of radial and Goldstone modes.

This page is tree-level and classical unless explicitly stated otherwise. Loop corrections replace the classical potential by an effective potential, whose gauge dependence and renormalization-scale dependence require extra care.

## Core idea

The Higgs potential is the smallest gauge-invariant scalar function that can select a nonzero electroweak vacuum. It does not give masses to gauge bosons by itself; the gauge-boson masses come from $|D_\mu H|^2$ after $H$ has a nonzero vacuum expectation value. The potential supplies the vacuum scale and the physical radial excitation.

There are two separate pieces of physics:

| Piece | Comes from | Main consequence |
|---|---|---|
| Vacuum magnitude | $V(H)$ | $H^\dagger H=v^2/2$ |
| Gauge-boson masses | $(D_\mu H)^\dagger(D^\mu H)$ | $W^\pm$ and $Z$ become massive |
| Higgs mass and self-couplings | expansion of $V(H)$ | $m_h^2=2\lambda v^2$, plus $h^3$ and $h^4$ interactions |

The common phrase “negative mass squared” refers to the coefficient of $H^\dagger H$ at the origin. It does not mean the physical Higgs boson has negative mass squared. The physical Higgs field is the radial fluctuation around the true minimum, where the curvature is positive.

## Setup and conventions

The Higgs-sector Lagrangian is

$$
\mathcal L_H=(D_\mu H)^\dagger(D^\mu H)-V(H),
$$

with

$$
D_\mu H
=
\left(\partial_\mu+igW_\mu^a\frac{\sigma^a}{2}+ig'\frac12B_\mu\right)H.
$$

The Higgs field has mass dimension one in four spacetime dimensions, so $H^\dagger H$ has dimension two. Renormalizability allows scalar operators of mass dimension at most four.

We use

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2,
\qquad
\mu^2>0,
\qquad
\lambda>0.
$$

The condition $\lambda>0$ makes the classical potential bounded below. An additive constant may always be included,

$$
V(H)\mapsto V(H)+V_0,
$$

but in nongravitational flat-spacetime QFT this constant does not affect particle masses or scattering amplitudes. It matters once gravity or cosmology is included.

## Why this is the most general renormalizable potential

With one Higgs doublet, the basic gauge-invariant scalar polynomial is

$$
H^\dagger H.
$$

The possible renormalizable terms are therefore

$$
V(H)=V_0+aH^\dagger H+b(H^\dagger H)^2.
$$

Writing $a=-\mu^2$ and $b=\lambda$ gives the usual form. There is no gauge-invariant linear term in $H$, because $H$ is not a singlet. There is no independent cubic polynomial built from a single commuting $SU(2)$ doublet.

A tempting expression is

$$
\epsilon_{ij}H^iH^j,
$$

but for one bosonic doublet it vanishes:

$$
\epsilon_{ij}H^iH^j=H^1H^2-H^2H^1=0.
$$

Thus the minimal Higgs potential really has only two nontrivial parameters at the renormalizable classical level: $\mu^2$ and $\lambda$.

## Minimization

Let

$$
\rho=H^\dagger H\ge0.
$$

Then

$$
V(\rho)=-\mu^2\rho+\lambda\rho^2.
$$

The stationary condition is

$$
\frac{dV}{d\rho}=-\mu^2+2\lambda\rho=0,
$$

so

$$
\rho=\frac{\mu^2}{2\lambda}.
$$

We define $v$ by

$$
\rho=\frac{v^2}{2},
$$

and therefore

$$
v^2=\frac{\mu^2}{\lambda}.
$$

The vacuum manifold before quotienting by gauge redundancy is the set of doublets with fixed length $H^\dagger H=v^2/2$. A convenient representative is the electrically neutral vacuum

$$
H_0=\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v
\end{pmatrix}.
$$

Gauge transformations move this representative around the gauge orbit. Physical quantities cannot depend on which gauge representative is chosen.

## Expansion around the vacuum

In unitary gauge,

$$
H=\frac{1}{\sqrt2}
\begin{pmatrix}
0\\v+h
\end{pmatrix},
\qquad
H^\dagger H=\frac{(v+h)^2}{2}.
$$

Insert this into the potential:

$$
V(h)
=
-\frac{\mu^2}{2}(v+h)^2
+\frac{\lambda}{4}(v+h)^4.
$$

Using $\mu^2=\lambda v^2$ and expanding gives

$$
V(h)=
-\frac{\lambda v^4}{4}
+\lambda v^2h^2
+\lambda vh^3
+\frac{\lambda}{4}h^4.
$$

Dropping the constant term,

$$
V(h)=\lambda v^2h^2+\lambda vh^3+\frac{\lambda}{4}h^4.
$$

The quadratic term is conventionally written as

$$
\frac12m_h^2h^2,
$$

so

$$
m_h^2=2\lambda v^2.
$$

This relation is tree-level. It is useful, but it is not a statement that the physical Higgs mass is “caused by” $v$ alone. The quartic coupling $\lambda$ is independent input in the minimal Standard Model.

## Parameter choices

The classical parameters $\mu^2$ and $\lambda$ are often traded for $v$ and $m_h$:

$$
\lambda=\frac{m_h^2}{2v^2},
\qquad
\mu^2=\lambda v^2=\frac{m_h^2}{2}.
$$

In terms of $m_h$ and $v$, the nonconstant potential is

$$
V(h)=
\frac12m_h^2h^2
+\frac{m_h^2}{2v}h^3
+\frac{m_h^2}{8v^2}h^4.
$$

The corresponding interaction terms in the Lagrangian are the negatives of the cubic and quartic terms in $V$:

$$
\mathcal L_{\rm int}\supset
-\frac{m_h^2}{2v}h^3
-\frac{m_h^2}{8v^2}h^4.
$$

If one writes

$$
\mathcal L_{\rm int}\supset
-\frac{\lambda_3}{3!}h^3
-\frac{\lambda_4}{4!}h^4,
$$

then the tree-level Standard Model values are

$$
\lambda_3=\frac{3m_h^2}{v},
\qquad
\lambda_4=\frac{3m_h^2}{v^2}.
$$

These self-interactions are important because they are the most direct low-energy probes of the shape of the Higgs potential itself.

## Vacuum scale versus Higgs mass

The vacuum scale $v$ and the Higgs mass $m_h$ answer different questions.

The scale $v$ sets the amount of electroweak symmetry breaking. It enters the gauge-boson masses through $|D_\mu H|^2$ and is related at tree level to the low-energy Fermi constant by

$$
G_F=\frac{1}{\sqrt2v^2}.
$$

The Higgs mass is the curvature of the potential in the radial direction:

$$
m_h^2=\left.\frac{d^2V}{dh^2}\right|_{h=0}.
$$

These are related only after specifying $\lambda$:

$$
m_h^2=2\lambda v^2.
$$

So $v$ fixes the weak scale, while $\lambda$ fixes how stiff the potential is in the radial direction. Confusing these two is the Higgs-sector version of confusing a valley's location with its curvature.

## Stability and the effective potential

At the classical level, $\lambda>0$ makes the potential bounded below. Quantum mechanically, the quartic coupling runs with scale. The loop-corrected effective potential is a useful tool for studying vacuum stability, but it brings subtleties that are not present in the tree-level page:

- the running coupling depends on the renormalization scheme and scale;
- the effective potential away from extrema can be gauge dependent;
- metastability questions involve both RG improvement and tunneling rates;
- higher-dimensional operators can change the potential at large field values.

Those issues belong to later pages on precision Standard Model physics, SMEFT, and effective potentials. The tree-level potential here is the starting point, not the final word on the electroweak vacuum.

## Common pitfalls

**Thinking the negative quadratic coefficient is a physical tachyon.** The negative coefficient of $H^\dagger H$ means the point $H=0$ is not the vacuum. The physical Higgs boson is the radial excitation around the true vacuum and has positive tree-level mass squared $m_h^2=2\lambda v^2$.

**Forgetting that $\mathcal L=T-V$.** The mass term in the potential is $+\frac12m_h^2h^2$, while the Lagrangian contains $-\frac12m_h^2h^2$. Mixing these signs is a reliable way to summon nonsense.

**Treating the additive constant as always irrelevant.** In flat-spacetime scattering without gravity, the constant in $V$ can be dropped. In gravitational or cosmological questions, vacuum energy is physical input.

**Identifying $v$ with $m_h$.** The vacuum scale $v$ controls weak-boson masses and the Fermi constant at tree level. The physical Higgs mass also depends on $\lambda$.

**Using the tree-level potential for all stability questions.** Vacuum stability is a loop-level and RG-improved question. The tree-level potential gives the vocabulary; it does not settle high-field metastability.

## Relations to other pages

- [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/) fixes the representation and neutral vacuum direction used here.
- [Gauge Boson Masses](/gauge-theories-standard-model/higgs-sector/gauge-boson-masses/) derives the $W$ and $Z$ masses from $|D_\mu H|^2$ after $H^\dagger H=v^2/2$ is chosen.
- [Higgs Boson Couplings](/gauge-theories-standard-model/higgs-sector/higgs-boson-couplings/) expands the kinetic and potential terms to obtain $hVV$, $hff$, $h^3$, and $h^4$ interactions.
- [Fermi Theory Limit](/gauge-theories-standard-model/electroweak/fermi-theory-limit/) relates $v$ to the low-energy weak-interaction strength at tree level.
- The planned Standard Model Lagrangian page later assembles the Higgs potential with the gauge, fermion, and Yukawa sectors.

## Research status

The tree-level potential and the relations

$$
v^2=\frac{\mu^2}{\lambda},
\qquad
m_h^2=2\lambda v^2
$$

are textbook-standard in the minimal Standard Model. The main convention dependence is whether one writes $V=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2$, $V=-m^2|H|^2+\lambda|H|^4$, or $V=\lambda(H^\dagger H-v^2/2)^2$ up to constants.

Active questions begin when the potential is used as a window into ultraviolet physics. Higgs self-coupling measurements test the shape of the potential near the vacuum. Vacuum stability and metastability depend on the loop-corrected running of $\lambda$. SMEFT operators such as $(H^\dagger H)^3$ parameterize possible deviations from the minimal quartic potential.

## Exercises

### Exercise 1: Minimize the potential

Let $\rho=H^\dagger H$. Minimize

$$
V(\rho)=-\mu^2\rho+\lambda\rho^2
$$

for $\mu^2>0$ and $\lambda>0$.

<details>
<summary><strong>Solution</strong></summary>

The stationary condition is

$$
\frac{dV}{d\rho}=-\mu^2+2\lambda\rho=0,
$$

so

$$
\rho=\frac{\mu^2}{2\lambda}.
$$

Defining $\rho=v^2/2$ gives

$$
v^2=\frac{\mu^2}{\lambda}.
$$

The second derivative is $d^2V/d\rho^2=2\lambda>0$, so this is a minimum.

</details>

### Exercise 2: Expand the potential

Starting from

$$
H=\frac{1}{\sqrt2}\begin{pmatrix}0\\v+h\end{pmatrix},
$$

show that, up to a constant,

$$
V(h)=\lambda v^2h^2+\lambda vh^3+\frac{\lambda}{4}h^4.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute $H^\dagger H=(v+h)^2/2$:

$$
V(h)=-\frac{\mu^2}{2}(v+h)^2+\frac{\lambda}{4}(v+h)^4.
$$

Using $\mu^2=\lambda v^2$, expand:

$$
V(h)=
-\frac{\lambda v^2}{2}(v^2+2vh+h^2)
+\frac{\lambda}{4}(v^4+4v^3h+6v^2h^2+4vh^3+h^4).
$$

The linear terms cancel, and the result is

$$
V(h)=-\frac{\lambda v^4}{4}+\lambda v^2h^2+\lambda vh^3+\frac{\lambda}{4}h^4.
$$

Dropping the constant gives the stated expression.

</details>

### Exercise 3: Extract the Higgs mass

Use the expansion in Exercise 2 to show that $m_h^2=2\lambda v^2$.

<details>
<summary><strong>Solution</strong></summary>

The quadratic term in a real scalar potential is

$$
\frac12m_h^2h^2.
$$

The Higgs potential has quadratic term $\lambda v^2h^2$. Therefore

$$
\frac12m_h^2=\lambda v^2,
\qquad
m_h^2=2\lambda v^2.
$$

</details>

### Exercise 4: Show that the antisymmetric doublet contraction vanishes

For one commuting Higgs doublet $H^i$, show that $\epsilon_{ij}H^iH^j=0$.

<details>
<summary><strong>Solution</strong></summary>

Using $\epsilon_{12}=1$ and $\epsilon_{21}=-1$,

$$
\epsilon_{ij}H^iH^j=H^1H^2-H^2H^1.
$$

The components of a classical bosonic scalar field commute, so $H^1H^2=H^2H^1$. Hence the expression vanishes. This is why there is no independent quadratic invariant of the form $HH$ for a single Higgs doublet.

</details>

### Exercise 5: Convert self-coupling conventions

Given

$$
V(h)\supset \frac{m_h^2}{2v}h^3+\frac{m_h^2}{8v^2}h^4,
$$

find $\lambda_3$ and $\lambda_4$ if the interaction Lagrangian is written as

$$
\mathcal L_{\rm int}\supset
-\frac{\lambda_3}{3!}h^3
-\frac{\lambda_4}{4!}h^4.
$$

<details>
<summary><strong>Solution</strong></summary>

Since $\mathcal L_{\rm int}=-V_{\rm int}$,

$$
\frac{\lambda_3}{3!}=\frac{m_h^2}{2v},
\qquad
\frac{\lambda_4}{4!}=\frac{m_h^2}{8v^2}.
$$

Thus

$$
\lambda_3=\frac{3m_h^2}{v},
\qquad
\lambda_4=\frac{3m_h^2}{v^2}.
$$

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §87, for the Standard Model gauge and Higgs sector and the unitary-gauge expansion.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–29, for the Higgs mechanism, the weak sector, and the physical Higgs boson in electroweak theory.
- Coleman, *Aspects of Symmetry*, Ch. 5, “Secret Symmetry,” for the conceptual relation between spontaneous symmetry breaking, gauge fields, and the Higgs phenomenon.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and spontaneously broken gauge theories.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9, for the Standard Model as an effective theory and higher-dimensional deformations of the Higgs sector.

## Version history

- **2026-06-18:** Updated links to Gauge Boson Masses and Higgs Boson Couplings.
- **2026-06-18:** Initial standardized page.
