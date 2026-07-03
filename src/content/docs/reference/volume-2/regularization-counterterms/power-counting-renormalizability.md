---
title: "Power-Counting Renormalizability"
description: "How engineering dimensions and superficial degree of divergence predict which counterterms are needed in perturbative QFT."
sidebar:
  label: "Power-Counting Renormalizability"
  order: 6
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman, renormalization lectures; Srednicki §§17–29; Schwartz chs. 21–23; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Zinn-Justin, renormalization chapters."
topics:
  - power counting
  - superficial degree of divergence
  - renormalizability
  - relevant operators
  - marginal operators
  - irrelevant operators
  - effective field theory
canonicalTopics:
  - power-counting-renormalizability
  - superficial-degree-of-divergence
  - relevant-irrelevant-marginal
  - renormalizable-interaction
researchStatus:
  established:
    - "Power counting gives a standard first diagnostic for which local counterterms can be required by ultraviolet divergences in perturbation theory."
  active:
    - "Modern applications refine naive power counting with symmetries, gauge identities, equations of motion, operator bases, anomalous dimensions, and EFT expansion rules."
---

## Summary

**Power-counting renormalizability** is the criterion that engineering dimensions predict a finite list of counterterms is enough to absorb ultraviolet divergences order by order in perturbation theory.

For a scalar theory in $d$ spacetime dimensions with interactions

$$
\mathcal L_{\text{int}}
=-\sum_a g_a\mathcal O_a,
\qquad
\mathcal O_a\sim \partial^{r_a}\phi^{n_a},
$$

the engineering dimension of the coupling is

$$
[g_a]=d-\Delta_a^{\text{eng}},
\qquad
\Delta_a^{\text{eng}}=r_a+n_a\frac{d-2}{2}.
$$

The basic classification is:

| Interaction | Coupling dimension | Old perturbative name | Wilsonian name |
|---|---:|---|---|
| $[g_a]>0$ | positive | super-renormalizable | relevant |
| $[g_a]=0$ | zero | renormalizable | marginal by engineering dimension |
| $[g_a]<0$ | negative | nonrenormalizable | irrelevant by engineering dimension |

In four-dimensional $\lambda\phi^4$ theory, $[\lambda]=0$, and the superficial degree of divergence for a connected diagram with $E$ external scalar legs is

$$
D=4-E.
$$

Only diagrams with $E\le 4$ are superficially divergent, so the required local counterterms have the form of vacuum energy, mass, kinetic, and quartic terms. That is the power-counting reason $\phi^4$ theory in four dimensions is perturbatively renormalizable.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Power-counting operator tower in four-dimensional scalar field theory, separating relevant, marginal, and irrelevant operators by engineering dimension](/figures/renormalization-rg-eft/power-counting-operator-tower.svg)

<figcaption>

Power counting around the four-dimensional Gaussian fixed point sorts local scalar operators by engineering dimension. Operators below $\Delta=4$ have positive-dimension couplings, operators at $\Delta=4$ are marginal by engineering dimension, and operators above $\Delta=4$ form an EFT tower suppressed by powers of a heavy scale.

</figcaption>
</figure>

:::note[Power counting is a first diagnosis]
Power counting tells you what divergences are allowed by dimensions. It does not prove that every allowed divergence is present, and it does not include cancellations from symmetries, gauge identities, equations of motion, or special kinematics.
:::

## Prerequisites

You should know [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) and the idea that ultraviolet divergences are absorbed by local operators. You should also be comfortable with engineering dimensions from [Conventions and Notation](/renormalization-rg-eft/conventions/) and with the large-momentum estimates introduced in [Cutoff Regularization](/renormalization-rg-eft/regularization-counterterms/cutoff-regularization/).

This page is about **power counting**, not a full proof of renormalizability. Gauge theories, composite operators, and EFT operator bases require additional structure developed later.

## Core idea

At high loop momentum, propagators and vertices behave like powers of momentum. The superficial degree of divergence $D$ estimates the leading power of a loop integral before cancellations or subtractions. If the large-momentum region reduces schematically to

$$
\int^\Lambda dk\,k^{D-1},
$$

then:

| $D$ | Superficial behavior |
|---:|---|
| $D>0$ | power divergence |
| $D=0$ | logarithmic divergence |
| $D<0$ | superficially convergent |

The word **superficial** matters. A graph may be superficially convergent but contain divergent subgraphs. It may be superficially divergent but vanish or be softened by symmetry. Power counting is the map, not the whole hike.

The key question is:

> As perturbation theory goes to higher loop order, do ultraviolet divergences require only a finite set of local counterterms, or do they require new independent operators at every order?

If the answer is finite, the theory is power-counting renormalizable in the traditional sense. If the answer is infinite, the theory may still be an excellent EFT, but it is not renormalizable by old power-counting standards.

## Setup and conventions

Use natural units and $d$ spacetime dimensions. The action is dimensionless:

$$
[S]=0,
\qquad
[S]=\left[\int d^d x\,\mathcal L\right],
\qquad
[\mathcal L]=d.
$$

For a scalar field with canonical kinetic term,

$$
\mathcal L_{\text{kin}}
=\frac12\partial_\mu\phi\,\partial^\mu\phi,
$$

we have

$$
[\phi]=\frac{d-2}{2}.
$$

For a Dirac fermion,

$$
[\psi]=\frac{d-1}{2},
$$

and for a gauge field with kinetic term $F_{\mu\nu}F^{\mu\nu}$,

$$
[A_\mu]=\frac{d-2}{2}.
$$

A local operator $\mathcal O_i$ with engineering dimension $\Delta_i^{\text{eng}}$ has coupling dimension

$$
[g_i]=d-\Delta_i^{\text{eng}}.
$$

This number is the first power-counting diagnostic. It says how the coefficient scales before anomalous dimensions and loop corrections are included.

## Superficial degree of divergence

Consider a connected scalar graph built from propagators behaving as $1/k^2$ and vertices carrying $r_a$ derivatives. Let:

| Symbol | Meaning |
|---|---|
| $L$ | number of independent loop momenta |
| $I$ | number of internal scalar lines |
| $V_a$ | number of vertices of type $a$ |
| $E$ | number of external scalar lines |
| $r_a$ | number of derivatives at vertex $a$ |
| $n_a$ | number of scalar fields at vertex $a$ |

The superficial degree of divergence is

$$
D=dL-2I+\sum_a V_a r_a.
$$

The terms have a simple meaning:

- each loop integration contributes $d$ powers of momentum;
- each scalar propagator contributes $-2$ powers;
- each derivative in a vertex contributes $+1$ power.

The graph topology identities are

$$
L=I-\sum_a V_a+1,
$$

and

$$
\sum_a n_aV_a=2I+E.
$$

Using these identities gives the dimension-based form

$$
D
=d-E\frac{d-2}{2}
+\sum_a V_a\left(\Delta_a^{\text{eng}}-d\right),
$$

where

$$
\Delta_a^{\text{eng}}
=r_a+n_a\frac{d-2}{2}.
$$

Equivalently,

$$
D
=d-E[\phi]
-\sum_a V_a[g_a].
$$

This formula is the power-counting engine. If all couplings have nonnegative mass dimension, then increasing the number of vertices cannot make $D$ grow without bound. If some coupling has negative mass dimension, then diagrams with more such vertices can require counterterms of ever-increasing dimension.

## Example: scalar φ⁴ theory in four dimensions

For $\lambda\phi^4$ theory in $d=4$,

$$
[\phi]=1,
\qquad
[\lambda]=0,
\qquad
\Delta_{\phi^4}^{\text{eng}}=4.
$$

The general formula gives

$$
D=4-E.
$$

Therefore:

| External legs | $D$ | Possible local counterterms |
|---:|---:|---|
| $E=0$ | $4$ | vacuum energy |
| $E=2$ | $2$ | $\phi^2$, $\partial_\mu\phi\partial^\mu\phi$ |
| $E=4$ | $0$ | $\phi^4$ |
| $E\ge 6$ | $<0$ | no primitive superficial divergence |

The phrase **primitive** is important. A six-point graph may contain a divergent four-point subgraph. After the four-point subgraph is renormalized, the remaining overall six-point graph is superficially convergent.

This is why the counterterm Lagrangian for renormalizable $\mathbb Z_2$-symmetric scalar theory in four dimensions has the form

$$
\mathcal L_{\text{ct}}
=\delta\Lambda_{\text{vac}}
+\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4.
$$

The finite list of counterterms mirrors the finite list of superficially divergent amplitudes.

## Example: φ⁶ theory in four dimensions

Now add

$$
\mathcal L\supset -\frac{c_6}{6!}\phi^6.
$$

In four dimensions,

$$
[\phi]=1,
\qquad
[\phi^6]=6,
\qquad
[c_6]=-2.
$$

A graph with $V_6$ insertions of this vertex has

$$
D=4-E+2V_6
$$

when only $\phi^6$ vertices are counted in addition to marginal terms. Increasing $V_6$ can increase $D$. That means higher orders in perturbation theory can generate divergences requiring operators with more fields and more derivatives:

$$
\phi^8,
\qquad
\phi^{10},
\qquad
(\partial\phi)^2\phi^6,
\qquad
\ldots
$$

This is the old reason $\phi^6$ is called nonrenormalizable in four dimensions.

But the Wilsonian interpretation is not "throw it away." If $c_6\sim 1/M^2$, then at energies $Q\ll M$ the interaction is suppressed by $Q^2/M^2$ or by suitable powers of fields and masses. It belongs naturally in an EFT expansion.

## Example: four-fermion interactions

In four dimensions,

$$
[\psi]=\frac32.
$$

A four-fermion operator has dimension

$$
[(\bar\psi\Gamma\psi)(\bar\psi\Gamma\psi)]=6,
$$

so its coefficient has dimension

$$
[G]=-2.
$$

This is why the Fermi interaction has the schematic form

$$
\mathcal L_{\text{Fermi}}
\sim -G_F(\bar\psi\Gamma\psi)(\bar\psi\Gamma\psi),
\qquad
G_F\sim \frac{1}{M_W^2}.
$$

By old power counting it is nonrenormalizable. As an EFT below the $W$ mass, it is perfectly predictive order by order in $Q/M_W$. The negative mass dimension of $G_F$ is not a warning label saying "nonsense"; it is the power-counting announcement that the description has a cutoff scale.

## Relevant, marginal, and irrelevant

The Wilsonian terminology is more flexible than the old renormalizable/nonrenormalizable language.

Near the Gaussian fixed point, an operator with engineering dimension $\Delta_i^{\text{eng}}$ is classified by

$$
y_i=d-\Delta_i^{\text{eng}}=[g_i].
$$

| $y_i$ | Wilsonian name | Behavior toward the IR near the Gaussian fixed point |
|---:|---|---|
| $y_i>0$ | relevant | grows |
| $y_i=0$ | marginal | decided by loop corrections |
| $y_i<0$ | irrelevant | shrinks |

This is the same dimensional information as old power-counting renormalizability, but the interpretation is better. It tells us which deformations matter at long distance near a fixed point.

In four dimensions:

| Operator | Engineering dimension | Coupling dimension | Classification |
|---|---:|---:|---|
| $\phi$ | $1$ | $3$ | relevant, if symmetry allows |
| $\phi^2$ | $2$ | $2$ | relevant |
| $\phi^3$ | $3$ | $1$ | relevant, if symmetry allows |
| $\phi^4$ | $4$ | $0$ | marginal by engineering dimension |
| $\bar\psi i\gamma^\mu\partial_\mu\psi$ | $4$ | $0$ | kinetic term |
| $F_{\mu\nu}F^{\mu\nu}$ | $4$ | $0$ | kinetic term |
| $\bar\psi\gamma^\mu A_\mu\psi$ | $4$ | $0$ | marginal gauge interaction |
| $\phi^6$ | $6$ | $-2$ | irrelevant |
| $(\bar\psi\psi)^2$ | $6$ | $-2$ | irrelevant |

At an interacting fixed point, engineering dimensions are replaced by full scaling dimensions,

$$
\Delta_i=\Delta_i^{\text{eng}}+\gamma_i,
$$

and the classification can change. This is one reason power counting around the Gaussian fixed point is a beginning, not the final word.

## Super-renormalizable, renormalizable, and nonrenormalizable

The old terminology is still useful when used carefully.

A theory is **super-renormalizable** if all interactions have positive coupling dimension. Divergences become less severe at higher orders, and only finitely many loop orders may contain primitive divergences of a given type.

A theory is **power-counting renormalizable** if all interactions have nonnegative coupling dimension. Marginal couplings can produce logarithmic divergences to all orders, but the required counterterms belong to a finite operator set.

A theory is **nonrenormalizable by power counting** if at least one interaction has negative coupling dimension. Higher orders can require counterterms of ever-increasing dimension.

The classification depends on spacetime dimension. For example:

| Theory | Dimension | Coupling dimension | Power-counting status |
|---|---:|---:|---|
| $\phi^4$ | $d=4$ | $0$ | renormalizable |
| $\phi^4$ | $d=3$ | $1$ | super-renormalizable |
| $\phi^4$ | $d=5$ | $-1$ | nonrenormalizable |
| $\phi^3$ | $d=6$ | $0$ | renormalizable |
| Yang–Mills | $d=4$ | $0$ | renormalizable |
| four-fermion | $d=4$ | $-2$ | nonrenormalizable, useful as EFT |

The same Lagrangian term can change status when the dimension changes. This is why the $\epsilon$ expansion around four dimensions is natural for $\phi^4$ critical phenomena, while $\phi^3$ theory is naturally associated with six-dimensional power counting.

## Power counting with derivatives

Derivative interactions are counted by including powers of momentum in the vertices. For a scalar operator

$$
\mathcal O=\partial^{r}\phi^n,
$$

where $r$ is the number of derivatives, the engineering dimension is

$$
\Delta_{\mathcal O}^{\text{eng}}
=r+n\frac{d-2}{2}.
$$

In four dimensions, examples include:

| Operator | Dimension | Coupling dimension |
|---|---:|---:|
| $\phi^4$ | $4$ | $0$ |
| $(\partial\phi)^2\phi^2$ | $6$ | $-2$ |
| $(\partial\phi)^4$ | $8$ | $-4$ |
| $\phi^2\Box\phi^2$ | $6$ | $-2$ |

Derivative interactions are not pathological. They are exactly what EFT expects. Their negative coupling dimensions tell us the powers of the heavy scale that suppress them.

Derivative counting also explains why field redefinitions and equations of motion matter. Some derivative operators are redundant: their effects can be moved into other operators without changing the S-matrix. Power counting tells us the possible operator dimensions; it does not by itself choose an independent basis.

## Subdivergences and primitive divergences

The superficial degree of divergence $D$ refers to the overall divergence of a graph when all loop momenta become large together. A graph can also contain divergent subgraphs.

For example, in $\phi^4$ theory a two-loop six-point graph can be superficially convergent because $D=4-6=-2$. But it may contain a one-loop four-point subgraph with $D=0$. That subgraph requires the same $\phi^4$ counterterm already identified at one loop.

Renormalization proceeds recursively:

1. subtract divergent subgraphs using lower-order counterterms;
2. then examine the remaining overall divergence;
3. add a counterterm for the remaining local primitive divergence if needed.

Power counting tells us which primitive divergences can remain after subtractions. Locality ensures the required subtraction is local.

This recursive structure is the reason a finite counterterm list can control infinitely many diagrams in a renormalizable theory.

## Symmetries can improve power counting

Naive power counting deliberately ignores cancellations. Symmetry can change the actual divergence structure.

In QED, Ward identities relate the electron self-energy and vertex correction. In Yang–Mills theory, gauge invariance and BRST symmetry strongly restrict counterterms. In theories with chiral symmetry, mass terms may be forbidden or technically natural. Supersymmetry can cancel divergences that power counting alone would allow.

The safe rule is:

$$
\text{power counting gives the allowed danger; symmetry decides which dangers actually survive.}
$$

This matters especially in gauge theory. A naive cutoff may appear to generate a photon mass term

$$
\frac12m_\gamma^2A_\mu A^\mu,
$$

which would be relevant by dimension. Gauge invariance forbids it. A regulator or calculation that seems to require it is either breaking gauge invariance artificially or diagnosing an inconsistency.

## Renormalizable does not mean fundamental

Old terminology encouraged a bad metaphysics:

$$
\text{renormalizable} = \text{good},
\qquad
\text{nonrenormalizable} = \text{bad}.
$$

The Wilsonian lesson is subtler.

Renormalizable interactions dominate near the Gaussian fixed point at long distances. That is why they are often the leading terms in low-energy descriptions. But irrelevant interactions are generically present and encode short-distance physics. They are suppressed, not forbidden.

A renormalizable theory can still be only an EFT. QED, the Standard Model, and perturbative gravity are all best understood with scale in mind. Conversely, a nonrenormalizable theory can be highly predictive within its domain. Chiral perturbation theory, Fermi theory, heavy-quark effective theory, and gravitational EFT are standard examples.

The modern replacement for "is it renormalizable?" is:

> What is the expansion parameter, what is the cutoff or matching scale, and how many counterterms are needed at the desired accuracy?

## Predictivity at fixed order

Suppose an EFT has the schematic form

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{ren}}
+\sum_{\Delta>d}\frac{C_\Delta}{M^{\Delta-d}}\mathcal O_\Delta.
$$

At characteristic energy $Q\ll M$, an operator of dimension $\Delta$ contributes roughly as

$$
C_\Delta\left(\frac{Q}{M}\right)^{\Delta-d}
$$

relative to a dimension-$d$ interaction, up to field-normalization and loop factors.

If one wants accuracy through order $(Q/M)^N$, only operators with

$$
\Delta-d\le N
$$

need be included. Loops involving those operators may require counterterms at the same or higher order, but still only finitely many at fixed $N$.

This is the operational meaning of EFT predictivity. Infinite towers exist, but you do not need the whole tower to compute a finite-precision observable.

## Common pitfalls

**Treating $D<0$ as proof a graph is finite.** It is only superficially convergent. Divergent subgraphs may still be present.

**Forgetting derivative vertices.** Every derivative in an interaction can add powers of loop momentum. Derivative interactions must be counted explicitly.

**Ignoring symmetries.** Power counting may allow a counterterm that an exact symmetry forbids. Conversely, if the regulator breaks the symmetry, restoring it may require careful finite counterterms.

**Thinking marginal means exactly marginal.** Marginal by engineering dimension means $[g]=0$ at the Gaussian fixed point. Loop effects can make the coupling marginally relevant or marginally irrelevant.

**Calling nonrenormalizable theories useless.** Nonrenormalizable interactions are the backbone of EFT. The issue is not usefulness; it is domain of validity and power counting.

**Confusing power counting with naturalness.** Power counting says which operators are relevant, marginal, or irrelevant. Naturalness asks whether small coefficients are stable under quantum corrections and compatible with symmetries.

## Relations to other pages

This page explains why [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) sometimes form a finite list and sometimes an infinite tower. It prepares the more systematic discussion of [Renormalized Perturbation Theory](/renormalization-rg-eft/renormalized-perturbation-theory/) and the Wilsonian classification of [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

The EFT chapter will reinterpret negative-dimension couplings as controlled expansions in $Q/M$. The fixed-points chapter will replace engineering dimensions by full scaling dimensions near interacting fixed points. The local-operators chapter will refine the story using operator mixing, anomalous dimensions, redundant operators, and equations-of-motion operators.

## Research status

Power-counting renormalizability is settled as a perturbative engineering-dimension criterion. It remains an indispensable diagnostic in ordinary QFT, statistical field theory, and EFT.

The interesting modern work lies in refinements: choosing operator bases, handling redundancies, tracking anomalous dimensions, preserving gauge and spacetime symmetries, developing nonperturbative power-counting schemes, and organizing EFTs with multiple scales. In strongly coupled systems, naive engineering dimensions can be replaced by scaling dimensions that are not perturbatively close to their Gaussian values.

In quantum gravity, hydrodynamics, chiral perturbation theory, nonrelativistic EFT, SMEFT, and condensed-matter EFTs, power counting is not a dusty textbook test. It is the practical engine that tells you what to compute next.

## Exercises

### Exercise 1: Derive the scalar formula

For a scalar theory with vertices $\partial^{r_a}\phi^{n_a}$, derive

$$
D
=d-E\frac{d-2}{2}
+\sum_a V_a\left(\Delta_a^{\text{eng}}-d\right).
$$

<details><summary><strong>Solution</strong></summary>

Start from the large-momentum estimate

$$
D=dL-2I+\sum_a V_a r_a.
$$

For a connected graph,

$$
L=I-\sum_aV_a+1,
$$

and line counting gives

$$
\sum_a n_aV_a=2I+E.
$$

Substitute the loop identity into $D$:

$$
D=d\left(I-\sum_aV_a+1\right)-2I+\sum_aV_ar_a.
$$

This is

$$
D=d+(d-2)I+\sum_aV_a(r_a-d).
$$

Using

$$
I=\frac12\left(\sum_an_aV_a-E\right)
$$

gives

$$
D=d-E\frac{d-2}{2}
+\sum_aV_a\left(r_a+n_a\frac{d-2}{2}-d\right).
$$

Since

$$
\Delta_a^{\text{eng}}=r_a+n_a\frac{d-2}{2},
$$

the desired formula follows.

</details>

### Exercise 2: Which scalar interactions are renormalizable?

In four dimensions, classify $\phi^n$ interactions by power counting for $n=1,2,3,4,5,6$.

<details><summary><strong>Solution</strong></summary>

In $d=4$, a scalar has engineering dimension

$$
[\phi]=1.
$$

Therefore

$$
[\phi^n]=n,
\qquad
[g_n]=4-n.
$$

Thus:

| $n$ | $[g_n]$ | Classification |
|---:|---:|---|
| $1$ | $3$ | relevant, super-renormalizable if allowed |
| $2$ | $2$ | relevant, super-renormalizable |
| $3$ | $1$ | relevant, super-renormalizable if allowed |
| $4$ | $0$ | marginal by engineering dimension, renormalizable |
| $5$ | $-1$ | irrelevant, nonrenormalizable by power counting |
| $6$ | $-2$ | irrelevant, nonrenormalizable by power counting |

A symmetry such as $\phi\to-\phi$ can forbid odd powers.

</details>

### Exercise 3: Four-fermion power counting

Show that a four-fermion interaction in four dimensions has coefficient of mass dimension $-2$.

<details><summary><strong>Solution</strong></summary>

The Dirac kinetic term is

$$
\bar\psi i\gamma^\mu\partial_\mu\psi,
$$

which has dimension $4$. Since $[\partial_\mu]=1$ and $[\bar\psi]=[\psi]$, we get

$$
2[\psi]+1=4,
$$

so

$$
[\psi]=\frac32.
$$

A four-fermion operator has dimension

$$
4\times\frac32=6.
$$

The Lagrangian density has dimension $4$, so the coefficient has dimension

$$
4-6=-2.
$$

Thus the interaction is nonrenormalizable by four-dimensional power counting, but it is a valid EFT interaction suppressed by a heavy scale squared.

</details>

### Exercise 4: Why φ⁴ has only finitely many primitive divergences

Use $D=4-E$ in four-dimensional $\phi^4$ theory to explain why primitive divergences require only vacuum, two-point, and four-point counterterms.

<details><summary><strong>Solution</strong></summary>

For $E=0$, $D=4$, so vacuum diagrams can be divergent and require a vacuum-energy counterterm. For $E=2$, $D=2$, so the divergent local polynomial can include a constant and a $p^2$ term, corresponding to mass and kinetic counterterms. For $E=4$, $D=0$, so the divergence is logarithmic and momentum independent at the primitive level, corresponding to a $\phi^4$ counterterm. For $E\ge6$, $D<0$, so there are no primitive superficial divergences after subdivergences are subtracted. Therefore the finite counterterm set is

$$
1,
\qquad
\phi^2,
\qquad
\partial_\mu\phi\partial^\mu\phi,
\qquad
\phi^4.
$$

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on renormalization and counterterms.
- Mark Srednicki, *Quantum Field Theory*, especially sections on higher-order corrections, renormalizability, RG, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 21–23.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG, and critical phenomena.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on dimensional analysis, power counting, and matching.

## Version history

- 2026-06-16: First polished draft. Derived superficial degree of divergence, classified scalar and fermion interactions, separated old renormalizability from Wilsonian relevance, and connected power counting to EFT predictivity.
