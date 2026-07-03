---
title: "Yang–Mills Beta Function"
description: "Computes and organizes the one-loop Yang–Mills beta function, separating gauge, ghost, fermion, and scalar contributions and explaining the origin of asymptotic freedom."
sidebar:
  label: "Yang–Mills Beta Function"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§73 and 78; Schwartz Ch. 26; Weinberg Vol. II gauge-renormalization sections; Wilson–Kogut for RG context."
topics:
  - Yang–Mills theory
  - beta function
  - asymptotic freedom
  - background field gauge
  - dimensional regularization
  - group theory factors
canonicalTopics:
  - yang-mills-beta-function
  - asymptotic-freedom
  - non-abelian-running-coupling
  - gauge-renormalization
researchStatus:
  established:
    - "The one-loop Yang–Mills beta-function coefficient is universal and is the standard perturbative origin of asymptotic freedom."
  active:
    - "Higher-loop running, thresholds, scheme choices, finite-temperature effects, lattice definitions, and strongly coupled regimes require additional machinery beyond this one-loop template."
---

## Summary

This page derives the one-loop beta-function ledger for a four-dimensional Yang–Mills theory. For gauge group $G$ with gauge coupling $g$, adjoint quadratic Casimir $C_A$, Dirac fermions in representations $R_f$, and complex scalars in representations $R_s$, the one-loop beta function is

$$
\beta(g)
\equiv
\mu\frac{dg}{d\mu}
=
-\frac{g^3}{(4\pi)^2}b_0+O(g^5),
$$

where

$$
\boxed{
 b_0
 =
 \frac{11}{3}C_A
 -\frac{4}{3}\sum_{\text{Dirac }f}T(R_f)
 -\frac{1}{3}\sum_{\text{complex }s}T(R_s)
 }.
$$

For pure Yang–Mills theory,

$$
b_0=\frac{11}{3}C_A,
\qquad
\beta(g)=-\frac{11C_A}{3}\frac{g^3}{(4\pi)^2}+O(g^5).
$$

For QCD with gauge group $SU(3)$ and $n_f$ Dirac quarks in the fundamental representation,

$$
C_A=3,
\qquad
T_F=\frac12,
$$

so

$$
b_0=11-\frac{2}{3}n_f,
\qquad
\beta(g_s)
=
-\frac{g_s^3}{(4\pi)^2}\left(11-\frac{2}{3}n_f\right)+O(g_s^5).
$$

Equivalently, for $\alpha_s=g_s^2/(4\pi)$,

$$
\mu\frac{d\alpha_s}{d\mu}
=
-\frac{b_0}{2\pi}\alpha_s^2+O(\alpha_s^3).
$$

<figure class="doc-figure" style="--figure-width: 45rem;">

![One-loop Yang–Mills beta-function contribution ledger](/figures/gauge-theories-standard-model/yang-mills-beta-function-flow.svg)

<figcaption>

The one-loop coefficient is a competition between gauge-boson plus ghost anti-screening and matter screening. In non-Abelian gauge theory the adjoint gauge field can dominate, making the coupling weaker at short distances.

</figcaption>
</figure>

The sign is the headline. QED-like charged matter screens charge and tends to make $\beta(g)$ positive. Non-Abelian gauge bosons and ghosts produce the opposite sign. When the gauge contribution wins, the theory is asymptotically free.

## What is being calculated

A beta function measures how a renormalized coupling changes with the renormalization scale:

$$
\beta(g)=\mu\frac{dg}{d\mu}.
$$

This page calculates the universal one-loop coefficient $b_0$. It does not redo every tensor integral in a fixed gauge from scratch. Instead, it gives the reusable calculation architecture:

1. choose dimensional regularization and a gauge-invariant organization of counterterms;
2. isolate the divergent coefficient of the gauge kinetic operator;
3. separate the group-theory factors from the loop integrals;
4. convert the coupling counterterm into $\beta(g)$.

This is exactly the level of calculation most readers need when moving between Yang–Mills theory, QCD, electroweak running, and Standard Model checks.

## Group-theory normalization

The generators in a representation $R$ obey

$$
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

The Dynkin index $T(R)$ is defined by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

The quadratic Casimir $C_R$ is defined by

$$
T_R^aT_R^a=C_R\mathbf 1_R.
$$

For the adjoint representation,

$$
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

For $SU(N)$ in the common fundamental normalization,

$$
T_F=\frac12,
\qquad
C_F=\frac{N^2-1}{2N},
\qquad
C_A=N.
$$

The one-loop beta function depends on $C_A$ and $T(R)$, not directly on $C_R$. The reason is that the running of the gauge coupling is extracted from two external adjoint gauge fields. Matter loops contribute through traces over two generators, hence $T(R)$.

## Renormalization setup

Work in $d=4-2\epsilon$ dimensions and define the bare coupling by

$$
g_0=\mu^\epsilon Z_g g.
$$

In a minimal subtraction scheme, the one-loop result can be written as

$$
Z_g
=
1-\frac{g^2}{(4\pi)^2}\frac{b_0}{2\epsilon}+O(g^4).
$$

Since $g_0$ is independent of $\mu$,

$$
0=\mu\frac{d}{d\mu}(\mu^\epsilon Z_g g).
$$

Expanding this equation to order $g^3$ gives

$$
\beta(g)=-\epsilon g-\frac{g^3}{(4\pi)^2}b_0+O(g^5).
$$

In four dimensions, take $\epsilon\to0$:

$$
\beta(g)=-\frac{g^3}{(4\pi)^2}b_0+O(g^5).
$$

This sign convention is worth tattooing on your notes, not your arm. A positive $b_0$ means a negative beta function.

## Why background field gauge is efficient

One can compute $b_0$ from ordinary gluon, ghost, and matter self-energy diagrams plus vertex renormalization. That works, but the bookkeeping is long. Background field gauge packages the calculation more cleanly.

Split the gauge field into a classical background field and a quantum fluctuation:

$$
A_\mu^a=\bar A_\mu^a+Q_\mu^a.
$$

Choose a gauge-fixing function that is covariant with respect to the background field. The resulting one-loop effective action for $\bar A$ remains invariant under background gauge transformations. Therefore the divergent two-background-field part must be part of the gauge-invariant operator

$$
-\frac14\bar F_{\mu\nu}^a\bar F^{a\mu\nu}.
$$

This means that the one-loop running can be extracted from a single gauge-invariant kinetic counterterm. In background field gauge the coupling and background-field renormalizations are tied together; schematically,

$$
Z_g Z_{\bar A}^{1/2}=1.
$$

That identity is the reason the two-point calculation is enough. Gauge invariance does the bookkeeping that ordinary gauges distribute among propagators and vertices.

## The one-loop ledger

The answer is easiest to remember as a contribution table.

| Loop type | Contribution to $b_0$ | Physical tendency |
|---|---:|---|
| gauge boson plus ghost | $+\frac{11}{3}C_A$ | anti-screening |
| Dirac fermion in $R$ | $-\frac{4}{3}T(R)$ | screening |
| Weyl fermion in $R$ | $-\frac{2}{3}T(R)$ | screening |
| complex scalar in $R$ | $-\frac{1}{3}T(R)$ | screening |
| real scalar in $R$ | $-\frac{1}{6}T(R)$ | screening |

The gauge-boson and ghost rows should be read together. Ghosts are not optional decoration: they are part of the gauge-fixed description of the physical gauge-boson contribution. Omitting them gives a gauge-dependent and wrong answer.

For a theory with Dirac fermions and complex scalars,

$$
b_0
=
\frac{11}{3}C_A
-\frac{4}{3}\sum_{\text{Dirac }f}T(R_f)
-\frac{1}{3}\sum_{\text{complex }s}T(R_s).
$$

For a theory written in two-component notation with left-handed Weyl fermions and real scalars, the same formula is

$$
b_0
=
\frac{11}{3}C_A
-\frac{2}{3}\sum_{\text{Weyl }f}T(R_f)
-\frac{1}{6}\sum_{\text{real }s}T(R_s).
$$

These two forms are the same bookkeeping in different field languages.

## Where the 11 over 3 comes from

In a covariant calculation, the gauge-sector coefficient is assembled from several diagrams:

- a loop with two cubic gauge vertices;
- a loop involving the quartic gauge vertex;
- a ghost loop;
- gauge-fixing-dependent pieces that cancel in the final gauge-invariant counterterm.

The separate diagrams are not individually a physical statement. Their sum is. After the tensor integrals and group contractions are combined, the pure gauge sector contributes

$$
b_0^{\mathrm{gauge+ghost}}=\frac{11}{3}C_A.
$$

The sign is opposite to ordinary electric screening. A heuristic way to say it is that non-Abelian gauge fields carry gauge charge and polarize the vacuum in a way that enhances the long-distance field, so the short-distance coupling is smaller. The actual calculation is the loop integral ledger above; the heuristic should not be used as a substitute for the ghosts.

## Matter contribution

A Dirac fermion loop with two external gauge fields contributes a trace over two generators:

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

The spin and loop integral give the coefficient

$$
b_0^{\mathrm{Dirac}}=-\frac43T(R).
$$

For $n_f$ Dirac fermions in the same representation $R$,

$$
b_0^{\mathrm{matter}}=-\frac43 n_f T(R).
$$

This term has the same sign pattern as QED. If $G$ is Abelian, $C_A=0$ and the matter term makes $b_0<0$, so

$$
\beta(g)>0.
$$

That is the perturbative statement of electric charge screening: the effective charge grows toward the ultraviolet.

## QCD specialization

For QCD,

$$
G=SU(3),
\qquad
C_A=3,
\qquad
T_F=\frac12.
$$

With $n_f$ active Dirac quark flavors,

$$
b_0
=
\frac{11}{3}(3)-\frac{4}{3}n_f\left(\frac12\right)
=11-\frac{2}{3}n_f.
$$

Thus

$$
\beta(g_s)
=
-\frac{g_s^3}{(4\pi)^2}
\left(11-\frac{2}{3}n_f\right)+O(g_s^5).
$$

Asymptotic freedom requires

$$
11-\frac{2}{3}n_f>0,
$$

or

$$
n_f<\frac{33}{2}.
$$

For the physically relevant values $n_f\le6$, the one-loop coefficient is positive and QCD is asymptotically free.

## Running coupling at one loop

The differential equation

$$
\mu\frac{dg}{d\mu}
=-\frac{b_0}{(4\pi)^2}g^3
$$

integrates to

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}
+
\frac{2b_0}{(4\pi)^2}\ln\frac{\mu}{\mu_0}.
$$

Equivalently,

$$
\alpha(\mu)
=
\frac{\alpha(\mu_0)}{1+\frac{b_0\alpha(\mu_0)}{2\pi}\ln(\mu/\mu_0)}
+O(\alpha^3).
$$

If $b_0>0$, then $\alpha(\mu)$ decreases as $\mu$ increases. This is asymptotic freedom.

It is often convenient to trade the dimensionless coupling for a scale:

$$
\Lambda
=
\mu\exp\left[-\frac{2\pi}{b_0\alpha(\mu)}\right]
$$

at one loop. This is dimensional transmutation: the logarithmic running converts a dimensionless coupling into a dynamically meaningful scale.

## Checks

### Abelian check

Set $C_A=0$. For Dirac matter with charge normalization encoded in $T(R)$,

$$
b_0=-\frac43\sum_fT(R_f),
$$

so

$$
\beta(g)=+\frac{g^3}{(4\pi)^2}\frac43\sum_fT(R_f)+O(g^5).
$$

This is the QED sign: charge grows toward short distances.

### Pure Yang–Mills check

Set all matter sums to zero:

$$
b_0=\frac{11}{3}C_A.
$$

For $SU(N)$,

$$
\beta(g)=-\frac{11N}{3}\frac{g^3}{(4\pi)^2}+O(g^5).
$$

The coupling becomes small in the ultraviolet.

### Multiplicity check

Matter multiplicities count all fields charged under the gauge group being renormalized. For example, in Standard Model running, an $SU(2)$ doublet has two weak components but its contribution to the $SU(3)$ beta function depends on its color representation. Conversely, a color triplet quark doublet contributes to the $SU(2)$ running with a color multiplicity of three. The representation being traced and the spectator multiplicities are separate pieces of bookkeeping.

## Common mistakes

**Flipping the beta-function sign.** In this convention,

$$
\beta(g)=-\frac{g^3}{(4\pi)^2}b_0.
$$

So $b_0>0$ means the coupling decreases in the ultraviolet.

**Omitting ghosts.** In non-Abelian gauge theory, ghost loops are required by gauge fixing and are essential for the gauge-invariant coefficient $11C_A/3$.

**Counting Weyl fermions as Dirac fermions.** A Dirac fermion is two Weyl fermions in conjugate representations. One left-handed Weyl fermion contributes $-2T(R)/3$ to $b_0$.

**Confusing $T(R)$ with $C_R$.** The beta function uses $T(R)$ for matter loops because the loop contains $\operatorname{tr}_R(T^aT^b)$. The quantity $C_R$ appears in other contexts, such as anomalous dimensions and potentials.

**Forgetting spectator multiplicities.** A field can be charged under several gauge groups. When computing the running of one group, trace over that group and multiply by dimensions of spectator representations.

**Treating the global form of the gauge group as visible in this perturbative coefficient.** The one-loop coefficient depends on the Lie algebra and representations of dynamical fields. Global-form choices affect line operators and bundles, not this local perturbative coefficient.

## Exercises

### Exercise 1: QCD with six active flavors

Compute $b_0$ for $SU(3)$ QCD with $n_f=6$ Dirac quarks.

<details><summary><strong>Solution</strong></summary>

For QCD,

$$
b_0=11-\frac{2}{3}n_f.
$$

With $n_f=6$,

$$
b_0=11-4=7.
$$

Therefore

$$
\beta(g_s)=-7\frac{g_s^3}{(4\pi)^2}+O(g_s^5).
$$

The theory is still asymptotically free.

</details>

### Exercise 2: Weyl versus Dirac bookkeeping

Show that two left-handed Weyl fermions in conjugate representations contribute the same amount to $b_0$ as one Dirac fermion in $R$.

<details><summary><strong>Solution</strong></summary>

A left-handed Weyl fermion in $R$ contributes

$$
-\frac23T(R).
$$

The conjugate representation has the same Dynkin index:

$$
T(\overline R)=T(R).
$$

Therefore two Weyl fermions, one in $R$ and one in $\overline R$, contribute

$$
-\frac23T(R)-\frac23T(\overline R)
=-\frac43T(R),
$$

which is the Dirac-fermion contribution.

</details>

### Exercise 3: Asymptotic freedom for SU(N) with fundamentals

For $SU(N)$ with $n_f$ Dirac fermions in the fundamental representation, find the one-loop condition for asymptotic freedom.

<details><summary><strong>Solution</strong></summary>

For $SU(N)$,

$$
C_A=N,
\qquad
T_F=\frac12.
$$

Thus

$$
b_0=\frac{11}{3}N-\frac{4}{3}n_f\frac12
=\frac{11}{3}N-\frac{2}{3}n_f.
$$

Asymptotic freedom requires $b_0>0$:

$$
\frac{11}{3}N-\frac{2}{3}n_f>0.
$$

Equivalently,

$$
n_f<\frac{11}{2}N.
$$

</details>

## Related pages

- [Yang–Mills Three-Gluon Vertex](/gauge-theories-standard-model/calculation-library/yang-mills-three-gluon-vertex/) derives the cubic interaction used in gauge-loop diagrams.
- [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/) gives the conceptual renormalization-story version of this result.
- [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/) explains the physical meaning of $\beta(g)<0$.
- [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/) specializes the formula to $SU(3)$ with quark matter.
- [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/) uses the integrated one-loop equation and threshold-aware refinements.

## References

Srednicki’s chapters on the non-Abelian beta function and background field gauge give a compact field-theoretic derivation. Schwartz’s Yang–Mills chapters provide a modern calculation-oriented route through gluon and ghost loops, one-loop renormalization, and the running coupling. Weinberg gives a systematic gauge-theory renormalization treatment, while Wilson and Kogut supply the broader renormalization-group viewpoint.

## Version history

- **2026-06-19:** Initial polished calculation-library draft.
