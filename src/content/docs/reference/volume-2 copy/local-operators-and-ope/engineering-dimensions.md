---
title: "Engineering Dimensions"
description: "Classical mass dimensions of fields, local operators, and couplings, and how they organize power counting before anomalous dimensions enter."
sidebar:
  label: "Engineering Dimensions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, dimensional analysis and renormalization sections; Coleman 1985, Dilatations; Wilson and Kogut 1974; Zinn-Justin 2021; Schwartz 2014, chs. 21–23."
topics:
  - engineering dimensions
  - local operators
  - power counting
  - relevance
  - upper critical dimension
canonicalTopics:
  - engineering-dimensions
  - local-operators
  - power-counting
researchStatus:
  established:
    - "Engineering dimensions are classical bookkeeping data fixed by units, kinetic terms, and the scaling convention being used."
  active:
    - "In modern EFTs, condensed-matter systems, nonrelativistic theories, fractonic systems, and theories with anisotropic scaling, choosing the correct engineering dimensions remains part of the physics setup."
---

## Summary

An **engineering dimension** is the dimension assigned to a field, coupling, or local operator by dimensional analysis before quantum anomalous dimensions are included. In relativistic QFT with $\hbar=c=1$, mass, energy, and inverse length all have dimension one. The action is dimensionless, so in $d$ spacetime dimensions

$$
[S]=0,
\qquad
[d^d x]=-d,
\qquad
[\mathcal L]=d.
$$

From the canonical scalar kinetic term,

$$
\mathcal L_{\text{kin}}=\frac12\partial_\mu\phi\,\partial^\mu\phi,
$$

one obtains

$$
[\phi]_{\text{eng}}=\frac{d-2}{2}.
$$

From the Dirac kinetic term,

$$
\mathcal L_{\text{kin}}=\bar\psi i\gamma^\mu\partial_\mu\psi,
$$

one obtains

$$
[\psi]_{\text{eng}}=\frac{d-1}{2}.
$$

Engineering dimensions are the first power-counting tool. If a local operator $\mathcal O_i$ has engineering dimension $\Delta_i^{\text{eng}}$ and appears in the action as

$$
S\supset \int d^d x\,g_i\mathcal O_i,
$$

then the coupling has engineering dimension

$$
[g_i]=d-\Delta_i^{\text{eng}}.
$$

This formula is not yet the full RG story. It is the classical starting point. Quantum corrections can change scaling dimensions, mix operators, and move marginal couplings away from marginality. But without engineering dimensions, there is no clean way to begin the discussion.

:::note[The main slogan]
Engineering dimensions answer the question: **what would scale counting say before loop corrections and anomalous dimensions are allowed to speak?**
:::

## Prerequisites

You should know the scale conventions in [Conventions and Notation](/renormalization-rg-eft/conventions/), especially the distinction between $\Lambda$, $\mu$, and physical scales. It is useful to have read [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

This page is deliberately classical. The next page, [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/), explains how renormalization changes the story.

## Core idea

Dimensional analysis is a statement about units. In natural units, there is one basic mass dimension. Coordinates carry negative mass dimension,

$$
[x^\mu]=-1,
$$

and derivatives carry positive mass dimension,

$$
[\partial_\mu]=1.
$$

The action appears in the path integral as $e^{iS}$ in Lorentzian signature or $e^{-S_E}$ in Euclidean signature, so the action is dimensionless. Therefore every term in the Lagrangian density must have total dimension $d$ in $d$ spacetime dimensions.

This gives a simple algorithm.

1. Fix the scaling convention.
2. Assign $[\partial_\mu]=1$ and $[d^d x]=-d$.
3. Use kinetic terms to determine field dimensions.
4. Add field and derivative dimensions to determine local-operator dimensions.
5. Use $[g_i]=d-\Delta_i^{\text{eng}}$ to determine coupling dimensions.

The algorithm is almost embarrassingly simple. Its consequences are not. It explains why $\phi^4$ theory is special in four dimensions, why $\phi^3$ theory is special in six dimensions, why four-fermion interactions are irrelevant in four dimensions, why the Fermi theory knows about a heavy scale, and why EFTs naturally contain infinite towers of higher-dimension operators.

## Setup and conventions

This page uses the default relativistic conventions of the volume:

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
\hbar=c=1.
$$

The metric signature affects signs in kinetic terms and propagators, but it does not affect mass dimensions.

Unless stated otherwise, $d$ denotes spacetime dimension. In particle-physics examples $d=4$. In critical phenomena one often writes $d=4-\varepsilon_{\text{crit}}$ near the upper critical dimension. In dimensional regularization for relativistic loop integrals this volume usually writes $d=4-2\epsilon$. These symbols serve different bookkeeping traditions; the dimension-counting logic is the same.

We write

$$
[X]
$$

for the mass dimension of $X$. When we want to emphasize that the dimension is the classical engineering dimension rather than the full scaling dimension, we write

$$
\Delta_{\mathcal O}^{\text{eng}}.
$$

The full scaling dimension at an interacting fixed point is usually denoted

$$
\Delta_{\mathcal O}=\Delta_{\mathcal O}^{\text{eng}}+\gamma_{\mathcal O,*},
$$

where $\gamma_{\mathcal O,*}$ is an anomalous contribution evaluated at the fixed point. That quantum correction belongs to the next page.

## Mass dimensions in relativistic QFT

The basic assignments are

$$
[x^\mu]=-1,
\qquad
[\partial_\mu]=1,
\qquad
[d^d x]=-d,
\qquad
[S]=0,
\qquad
[\mathcal L]=d.
$$

A local term in the action has the form

$$
S_i=\int d^d x\,g_i\mathcal O_i(x).
$$

Since $S_i$ is dimensionless,

$$
[g_i]+[\mathcal O_i]-d=0.
$$

Thus

$$
[g_i]=d-[\mathcal O_i].
$$

This one-line formula is the seed of power counting. If $[g_i]>0$, the coupling carries positive mass dimension. If $[g_i]=0$, it is dimensionless. If $[g_i]<0$, it must be accompanied by inverse powers of a mass scale.

The phrase "dimensionless coupling" means dimensionless under the chosen engineering scaling. It does not mean the coupling is constant under RG flow. A marginal coupling can have a nonzero beta function.

## Fields from kinetic terms

### Scalar fields

For a real scalar with canonical kinetic term,

$$
\mathcal L_{\text{kin}}=\frac12\partial_\mu\phi\,\partial^\mu\phi,
$$

the Lagrangian density has dimension $d$, while the term contains two derivatives and two fields. Therefore

$$
2+2[\phi]=d,
$$

so

$$
[\phi]_{\text{eng}}=\frac{d-2}{2}.
$$

In four dimensions, $[\phi]=1$.

A scalar mass term is

$$
\mathcal L\supset -\frac12m^2\phi^2.
$$

Since $[\phi^2]=d-2$, the coefficient has dimension two:

$$
[m^2]=2,
\qquad
[m]=1.
$$

This is why mass is a relevant parameter near the Gaussian fixed point in any relativistic dimension where the scalar kinetic term has the usual form.

### Fermions

For a Dirac fermion,

$$
\mathcal L_{\text{kin}}=\bar\psi i\gamma^\mu\partial_\mu\psi.
$$

The gamma matrices are dimensionless. The term contains one derivative and two fermion fields, so

$$
1+2[\psi]=d.
$$

Thus

$$
[\psi]_{\text{eng}}=\frac{d-1}{2}.
$$

In four dimensions, $[\psi]=3/2$.

A fermion mass term is

$$
\mathcal L\supset -m\bar\psi\psi.
$$

Since $[\bar\psi\psi]=d-1$, the coefficient has dimension one:

$$
[m]=1.
$$

### Gauge fields

With the convention

$$
D_\mu=\partial_\mu-igA_\mu,
$$

the covariant derivative has dimension one. If the gauge kinetic term is normalized in the standard canonical way,

$$
\mathcal L_{\text{kin}}=-\frac14 F_{\mu\nu}F^{\mu\nu},
$$

then $F_{\mu\nu}$ has dimension $d/2$ and

$$
[A_\mu]_{\text{eng}}=\frac{d-2}{2}.
$$

Since $gA_\mu$ must have dimension one,

$$
[g]=1-[A_\mu]=\frac{4-d}{2}.
$$

Thus gauge couplings are engineering-marginal in four dimensions. In non-Abelian gauge theory one sometimes writes the action with a prefactor $1/g^2$ and absorbs $g$ into the field strength definition. That is a different bookkeeping convention. The physics is the same, but engineering dimensions must be assigned consistently.

### Ghosts

In covariantly gauge-fixed Yang–Mills theory, the Faddeev–Popov ghost kinetic term is schematically

$$
\mathcal L_{\text{gh}}=\bar c\,\partial^2 c+\cdots.
$$

Thus

$$
[\bar c]+[c]+2=d.
$$

With the usual symmetric assignment,

$$
[c]=[\bar c]=\frac{d-2}{2}.
$$

Ghost fields are Grassmann-valued scalar fields in spacetime; their engineering dimension follows from their kinetic operator, not from spin-statistics intuition about ordinary particles.

## Local operators

A **local operator** is built from fields and derivatives at one spacetime point. Its engineering dimension is the sum of the engineering dimensions of its constituents.

For a scalar operator

$$
\mathcal O=(\partial)^{k}\phi^n,
$$

where $k$ is the number of derivatives, the engineering dimension is

$$
\Delta_{\mathcal O}^{\text{eng}}
=k+n\frac{d-2}{2}.
$$

Examples in $d=4$ are:

| Operator | Engineering dimension in four dimensions |
|---|---:|
| $\phi$ | $1$ |
| $\phi^2$ | $2$ |
| $\phi^4$ | $4$ |
| $\partial_\mu\phi\partial^\mu\phi$ | $4$ |
| $\phi^6$ | $6$ |
| $\bar\psi\psi$ | $3$ |
| $\bar\psi\gamma^\mu\psi$ | $3$ |
| $F_{\mu\nu}F^{\mu\nu}$ | $4$ |
| $(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi)$ | $6$ |

The table is not an operator basis. It ignores symmetries, total derivatives, equations of motion, gauge redundancies, flavor indices, and integration-by-parts identities. Its job is simpler: it tells us which operators are cheap or expensive in dimension counting.

## Couplings and relevance

If

$$
S\supset \int d^d x\,g_i\mathcal O_i,
$$

then

$$
[g_i]=d-\Delta_i^{\text{eng}}.
$$

This produces the Gaussian fixed-point classification:

| Operator type | Engineering condition | Coupling dimension | Gaussian name |
|---|---:|---:|---|
| relevant | $\Delta_i^{\text{eng}}<d$ | $[g_i]>0$ | grows toward the IR |
| marginal | $\Delta_i^{\text{eng}}=d$ | $[g_i]=0$ | decided by beta functions |
| irrelevant | $\Delta_i^{\text{eng}}>d$ | $[g_i]<0$ | suppressed toward the IR |

The phrase "toward the IR" assumes ordinary relativistic scaling and a Wilsonian flow that lowers the cutoff. In the renormalized perturbation theory convention $t=\log\mu$, the same linearized flow appears with the opposite direction of RG time.

### Why relevant operators dominate long distances

Suppose $\Delta_i^{\text{eng}}<d$. Define the dimensionless coupling

$$
\tilde g_i(\Lambda)=\Lambda^{\Delta_i^{\text{eng}}-d}g_i.
$$

As the cutoff is lowered, $\Lambda$ decreases. Since $\Delta_i^{\text{eng}}-d<0$, the dimensionless coupling grows. This is the Wilsonian reason mass terms and symmetry-breaking perturbations are usually important in the infrared.

For an irrelevant operator with $\Delta_i^{\text{eng}}>d$, the dimensionless coupling shrinks toward the IR. This does not mean the operator is false. It means its effect on low-energy observables is suppressed by powers of $Q/M$, where $Q$ is the process scale and $M$ is the scale suppressing the operator.

## Examples in four dimensions

### Scalar φ⁴ theory

In $d=4$,

$$
[\phi]=1.
$$

The interaction

$$
\mathcal L\supset -\frac{\lambda}{4!}\phi^4
$$

has

$$
[\phi^4]=4,
\qquad
[\lambda]=0.
$$

Thus $\phi^4$ is engineering-marginal in four dimensions.

The operator $\phi^6$ has dimension six, so

$$
\mathcal L\supset -\frac{c_6}{M^2}\phi^6
$$

has a coefficient suppressed by two powers of a heavy scale. This is an irrelevant interaction in the Gaussian sense, but it is a perfectly legitimate EFT correction.

### Yukawa theory

A Yukawa interaction has the form

$$
\mathcal L\supset -y\phi\bar\psi\psi.
$$

In $d$ dimensions,

$$
[\phi\bar\psi\psi]
=\frac{d-2}{2}+2\frac{d-1}{2}
=\frac{3d-4}{2}.
$$

Therefore

$$
[y]=d-\frac{3d-4}{2}=\frac{4-d}{2}.
$$

Yukawa couplings are engineering-marginal in four dimensions.

### Gauge theory

With $D_\mu=\partial_\mu-igA_\mu$,

$$
[g]=\frac{4-d}{2}.
$$

Gauge interactions are also engineering-marginal in four dimensions. This is the power-counting reason QED, Yang–Mills theory, Yukawa theory, and scalar quartic theory all meet in the same four-dimensional renormalization story.

### Four-fermion interactions

A four-fermion operator has engineering dimension

$$
[(\bar\psi\Gamma\psi)(\bar\psi\Gamma\psi)]
=2(d-1).
$$

The coefficient therefore has dimension

$$
[G]=d-2(d-1)=2-d.
$$

In four dimensions,

$$
[G]=-2.
$$

This is why the Fermi interaction is naturally written as

$$
\mathcal L_{\text{Fermi}}\sim \frac{1}{M^2}(\bar\psi\Gamma\psi)(\bar\psi\Gamma\psi),
$$

where $M$ is a heavy mass scale. In the Standard Model, the relevant heavy scale is set by electroweak physics.

## Upper critical dimensions

Engineering dimensions also identify upper critical dimensions. Consider scalar interactions

$$
\mathcal L\supset g_n\phi^n.
$$

The operator dimension is

$$
[\phi^n]=n\frac{d-2}{2}.
$$

The coupling is engineering-marginal when

$$
d=n\frac{d-2}{2}.
$$

Solving gives

$$
d_c=\frac{2n}{n-2}.
$$

Thus:

| Interaction | Upper critical dimension |
|---|---:|
| $\phi^3$ | $6$ |
| $\phi^4$ | $4$ |
| $\phi^6$ | $3$ |

The upper critical dimension is the dimension where the coupling first becomes marginal by engineering counting. Below it, fluctuations become more important and the interaction tends to be relevant. This is why the Wilson–Fisher fixed point is naturally studied near $d=4$ for $\phi^4$ theory.

:::tip[Power counting is a starting point, not a verdict]
Engineering marginality means "classically marginal." Quantum beta functions decide whether a marginal interaction is marginally relevant, marginally irrelevant, exactly marginal, or part of a line or manifold of fixed points.
:::

## Derivatives, total derivatives, and bases

Derivatives raise engineering dimension. For example, in four dimensions,

$$
[\phi^2]=2,
\qquad
[(\partial_\mu\phi)(\partial^\mu\phi)]=4,
\qquad
[\phi^2(\partial_\mu\phi)(\partial^\mu\phi)]=6.
$$

In an action, not every expression with the same engineering dimension is independent. Integration by parts can relate operators:

$$
\int d^d x\,\phi\Box\phi
=-\int d^d x\,\partial_\mu\phi\partial^\mu\phi
$$

up to boundary terms. Equations of motion can also remove some operators from an on-shell EFT basis. Symmetries can forbid operators. Gauge invariance can require derivatives to appear as covariant derivatives or field strengths.

Engineering dimension tells you how expensive an operator is. It does not tell you whether it is independent.

The basis question is subtler:

$$
\text{allowed by dimension}
\quad\not\Rightarrow\quad
\text{independent in an operator basis}.
$$

That distinction becomes essential in the later pages on operator mixing, redundant operators, and equation-of-motion operators.

## Charges, currents, and stress tensors

Some important operator dimensions can be guessed from integrated quantities.

A conserved internal-symmetry charge has the form

$$
Q=\int d^{d-1}\mathbf x\,j^0(t,\mathbf x).
$$

Since a charge is dimensionless,

$$
[j^0]=d-1.
$$

Lorentz covariance then gives the same engineering dimension to the current components:

$$
[j^\mu]_{\text{eng}}=d-1.
$$

Similarly, the stress tensor appears in the conserved momentum

$$
P^\mu=\int d^{d-1}\mathbf x\,T^{0\mu}.
$$

Since $[P^\mu]=1$,

$$
[T^{\mu\nu}]_{\text{eng}}=d.
$$

At conformal fixed points, conserved currents and the stress tensor usually have protected full scaling dimensions $d-1$ and $d$, respectively, subject to the usual assumptions of unitarity and conservation. This protection is not merely engineering dimensional analysis; it follows from symmetry and shortening conditions. The engineering argument explains why those values are natural.

## Relation to EFT power counting

An EFT Lagrangian below a heavy scale $M$ is often organized as

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\le d}
+\sum_i\frac{C_i}{M^{\Delta_i-d}}\mathcal O_i,
\qquad
\Delta_i>d.
$$

Here $C_i$ is dimensionless if $\mathcal O_i$ has engineering dimension $\Delta_i$. At process energy $Q\ll M$, an insertion of $\mathcal O_i$ typically contributes with a suppression of order

$$
\left(\frac{Q}{M}\right)^{\Delta_i-d},
$$

up to couplings, loop factors, symmetry factors, and kinematic details.

This is why engineering dimensions are not merely a classification device for old-fashioned renormalizability. They are the backbone of EFT predictivity: to compute to a fixed order in $Q/M$, only finitely many operators are needed.

## Beyond relativistic engineering dimensions

This page uses ordinary relativistic scaling, where time and space scale in the same way. Some systems use a different scaling convention. For example, near a Lifshitz fixed point one may scale

$$
t\to b^z t,
\qquad
\mathbf x\to b\mathbf x,
$$

with dynamical exponent $z\ne1$. In nonrelativistic EFTs, the engineering dimensions of fields and couplings depend on the nonrelativistic kinetic operator and on the power counting appropriate to the problem.

The lesson is not that the formulas on this page apply unchanged everywhere. The lesson is that engineering dimensions are always defined relative to a chosen scaling problem. The default relativistic formulas are the correct starting point for the relativistic QFT and critical-phenomena pages in this volume.

## Common pitfalls

**Engineering dimension is not scaling dimension in an interacting theory.** At an interacting fixed point, anomalous dimensions change scaling exponents. Engineering dimensions are the classical starting point.

**Dimensionless does not mean constant.** A dimensionless coupling can run. Four-dimensional gauge, Yukawa, and quartic scalar couplings are engineering-marginal, but their beta functions decide their actual behavior.

**Irrelevant does not mean unphysical.** Irrelevant operators are suppressed at low energies, but they encode the leading effects of heavy physics in EFT.

**Relevant does not mean important in every situation.** A relevant operator can be forbidden by a symmetry, tuned to zero, or absent because the system is studied on a critical surface.

**Operator dimension is not basis independence.** Two operators of the same dimension may be related by integration by parts, equations of motion, or identities. Dimension counting is only the first sieve.

**Canonical kinetic terms matter.** If fields are rescaled, their engineering dimensions and coupling dimensions must be tracked consistently. A noncanonical normalization can hide the usual power counting.

**The symbol $d$ must be interpreted.** In dimensional regularization near four dimensions, $d=4-2\epsilon$ is common. In the critical $\epsilon$ expansion, $d=4-\varepsilon_{\text{crit}}$ is common. Do not mix the two small parameters by accident.

## Relations to other pages

[Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) uses engineering dimensions to explain old renormalizability. This page generalizes the bookkeeping to arbitrary local operators and prepares the operator-basis viewpoint.

[Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) explains the Wilsonian meaning of the classification near a fixed point. Engineering dimensions give the Gaussian version of that classification.

[Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/) explains how the full dimension differs from the engineering dimension once operators are renormalized.

[Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/) explain what happens when many operators share the same quantum numbers and cannot be renormalized one by one.

[Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) later turns this dimension counting into the practical EFT expansion in $Q/M$.

## Research status

Engineering dimensions themselves are settled. The nontrivial work is choosing the right scaling convention and operator basis for the physical problem. In relativistic perturbative QFT, the default assignments on this page are standard. In EFTs with multiple scales, nonrelativistic systems, finite-density systems, anisotropic fixed points, hydrodynamic EFTs, and fractonic or subsystem-symmetric theories, the appropriate engineering dimensions can be more problem-dependent.

The deeper research questions begin when engineering dimensions collide with quantum effects: anomalous dimensions, operator mixing, dangerously irrelevant operators, exactly marginal directions, and redundant directions in theory space.

## Exercises

### Exercise 1: Scalar and fermion dimensions

Derive the engineering dimensions of a real scalar field and a Dirac fermion in $d$ spacetime dimensions from their kinetic terms.

<details><summary><strong>Solution</strong></summary>

For a scalar,

$$
\mathcal L_{\text{kin}}=\frac12\partial_\mu\phi\partial^\mu\phi.
$$

The Lagrangian density has dimension $d$. The kinetic term has dimension

$$
2+2[\phi].
$$

Thus

$$
2+2[\phi]=d,
\qquad
[\phi]=\frac{d-2}{2}.
$$

For a Dirac fermion,

$$
\mathcal L_{\text{kin}}=\bar\psi i\gamma^\mu\partial_\mu\psi.
$$

The gamma matrices are dimensionless, so

$$
1+2[\psi]=d,
\qquad
[\psi]=\frac{d-1}{2}.
$$

</details>

### Exercise 2: Upper critical dimension of φⁿ

For a scalar interaction $g_n\phi^n$, show that the upper critical dimension is

$$
d_c=\frac{2n}{n-2}.
$$

Check the cases $n=3,4,6$.

<details><summary><strong>Solution</strong></summary>

The engineering dimension of $\phi$ is

$$
[\phi]=\frac{d-2}{2}.
$$

Thus

$$
[\phi^n]=n\frac{d-2}{2}.
$$

The interaction is engineering-marginal when

$$
[\phi^n]=d.
$$

Therefore

$$
n\frac{d-2}{2}=d.
$$

Solving,

$$
nd-2n=2d,
\qquad
(n-2)d=2n,
\qquad
d_c=\frac{2n}{n-2}.
$$

For $n=3$, $d_c=6$. For $n=4$, $d_c=4$. For $n=6$, $d_c=3$.

</details>

### Exercise 3: Four-fermion suppression

In four spacetime dimensions, compute the engineering dimension of

$$
(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi).
$$

What dimension must its coefficient have?

<details><summary><strong>Solution</strong></summary>

In four dimensions,

$$
[\psi]=\frac{4-1}{2}=\frac32.
$$

Therefore

$$
[\bar\psi\gamma^\mu\psi]=[\bar\psi]+[\psi]=3.
$$

The four-fermion operator has dimension

$$
3+3=6.
$$

Since the Lagrangian density has dimension four, the coefficient has dimension

$$
4-6=-2.
$$

Thus it is naturally written as $C/M^2$, with $C$ dimensionless.

</details>

### Exercise 4: Gauge coupling away from four dimensions

Using $D_\mu=\partial_\mu-igA_\mu$ and $[A_\mu]=(d-2)/2$, show that

$$
[g]=\frac{4-d}{2}.
$$

What is $[g]$ in $d=4-2\epsilon$?

<details><summary><strong>Solution</strong></summary>

The covariant derivative must have dimension one. Therefore

$$
[g]+[A_\mu]=1.
$$

Using

$$
[A_\mu]=\frac{d-2}{2},
$$

we find

$$
[g]=1-\frac{d-2}{2}=\frac{4-d}{2}.
$$

In $d=4-2\epsilon$,

$$
[g]=\frac{4-(4-2\epsilon)}{2}=\epsilon.
$$

This is why dimensional regularization often writes the bare gauge coupling with a factor of $\mu^\epsilon$ near four dimensions.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for scale transformations, dimensions, and the transition from classical to anomalous scaling.
- Mark Srednicki, *Quantum Field Theory*, for dimensional analysis, renormalizability, and EFT power counting.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, nonrenormalizable theories, and the renormalization group.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the relation between engineering dimensions, critical dimensions, and RG near fixed points.
- C. P. Burgess, *Introduction to Effective Field Theory*, for EFT power counting and the interpretation of higher-dimension operators.

## Version history

- 2026-06-17: First polished draft. Added relativistic engineering dimensions, field dimensions, coupling dimensions, upper critical dimensions, EFT interpretation, pitfalls, and exercises.
