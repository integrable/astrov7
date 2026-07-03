---
title: "Soft-Collinear Effective Theory"
description: "SCET as the effective field theory for energetic jets, soft radiation, factorization, and resummation of large logarithms."
sidebar:
  label: "Soft-Collinear Effective Theory"
  order: 70
level: Advanced
status: "Polished draft"
source: "Bauer, Fleming, Pirjol, and Stewart 2000–2002; Beneke et al.; Becher and Neubert; Schwartz 2014, QCD and factorization chapters; Burgess 2020, matching and power counting."
topics:
  - soft-collinear effective theory
  - factorization
  - jets
  - resummation
  - Wilson lines
  - rapidity divergences
canonicalTopics:
  - scet
  - soft-collinear-factorization
  - jet-effective-theory
researchStatus:
  established:
    - "SCET is the standard EFT framework for separating hard, collinear, and soft dynamics in high-energy processes with energetic light particles and jet-like final states."
  active:
    - "Precision factorization, subleading-power corrections, Glauber modes, rapidity evolution, jet substructure, and multi-differential collider observables remain active research areas."
---

## Summary

**Soft-collinear effective theory**, or **SCET**, is the effective field theory for processes with energetic particles moving close to lightlike directions. It is the natural language for jets, endpoint spectra, Sudakov logarithms, factorization theorems, and the resummation of large logarithms in QCD and related gauge theories.

The basic physical situation is a hard process at scale $Q$ that produces energetic radiation with small invariant mass. A particle in an $n$-collinear jet has momentum components scaling as

$$
p^\mu\sim Q(\lambda^2,1,\lambda),
$$

where the components are $(n\cdot p,\bar n\cdot p,p_\perp)$, the vectors $n^\mu$ and $\bar n^\mu$ are lightlike with $n\cdot\bar n=2$, and $\lambda\ll 1$ measures the jet opening angle or invariant-mass hierarchy. The virtuality is

$$
p^2\sim Q^2\lambda^2.
$$

SCET separates hard physics at $Q$, collinear physics at jet scales, and soft radiation that communicates between energetic directions. The reward is a factorized description of observables:

$$
\text{observable}
\sim H(Q,\mu)\otimes J(\mu)\otimes S(\mu),
$$

where $H$ is a hard function, $J$ denotes jet functions, $S$ is a soft function, and $\otimes$ indicates the convolution variables appropriate to the observable.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![SCET mode and factorization map: a hard interaction at scale Q matches onto collinear sectors along n and nbar directions plus soft radiation; RG evolution connects hard, jet, and soft scales.](/figures/renormalization-rg-eft/scet-mode-factorization.svg)

<figcaption>

SCET matches a hard process at scale $Q$ onto collinear sectors moving along lightlike directions and soft radiation connecting them. Factorization separates hard, jet, and soft functions; RG evolution between their natural scales resums large Sudakov logarithms.

</figcaption>
</figure>

## Prerequisites

You should know [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/), [Gauge Theories and RG](/renormalization-rg-eft/gauge-theories-and-rg/), and basic QCD factorization ideas. Familiarity with light-cone coordinates, Wilson lines, and infrared singularities is helpful.

SCET is conceptually close to other EFTs but solves a different problem:

| EFT | Small parameter | Main degrees of freedom |
|---|---|---|
| HQET | $\Lambda_{\mathrm{QCD}}/m$ | heavy quark with fixed velocity |
| NRQCD | $v$ and $1/m$ | heavy quarks and antiquarks near threshold |
| SCET | $\lambda$ | energetic collinear fields and soft fields |

The small parameter in SCET is not a heavy-mass expansion by itself. It is an expansion in ratios of invariant masses and energies.

## Core idea

A high-energy event with jets contains modes whose momenta scale differently. For a two-jet process, one has hard fluctuations with virtuality $Q^2$, collinear fluctuations with much smaller invariant mass, and soft radiation with low momentum components. Ordinary QCD treats all of these at once. SCET separates them into fields with definite scaling.

The key EFT move is:

$$
\text{QCD at } Q
\longrightarrow
\text{hard Wilson coefficients}
+\text{collinear fields}
+\text{soft Wilson lines}
+\text{power corrections}.
$$

The hard modes are removed by matching. The collinear and soft modes remain dynamical. Gauge invariance is maintained separately in each sector through collinear and soft Wilson lines.

This separation is especially valuable when a fixed-order QCD expression contains large logarithms such as

$$
\alpha_s^n\log^m\frac{Q^2}{m_J^2},
\qquad m\le 2n,
$$

where $m_J$ is a jet mass or another lower scale. SCET turns the origin of these logarithms into RG evolution between hard, jet, and soft scales.

## Light-cone kinematics

Choose two lightlike vectors

$$
n^2=0,
\qquad
\bar n^2=0,
\qquad
n\cdot\bar n=2.
$$

Any four-vector decomposes as

$$
p^\mu=\frac{\bar n\cdot p}{2}n^\mu
+\frac{n\cdot p}{2}\bar n^\mu
+p_\perp^\mu.
$$

We write the component scaling as

$$
p^\mu\sim Q(n\cdot p/Q,\bar n\cdot p/Q,p_\perp/Q).
$$

An $n$-collinear momentum scales as

$$
p_n^\mu\sim Q(\lambda^2,1,\lambda),
$$

so

$$
p_n^2=(n\cdot p)(\bar n\cdot p)+p_\perp^2\sim Q^2\lambda^2.
$$

An opposite $\bar n$-collinear momentum scales as

$$
p_{\bar n}^\mu\sim Q(1,\lambda^2,\lambda).
$$

Soft and ultrasoft scalings depend on the version of SCET:

| Mode | Scaling | Typical context |
|---|---|---|
| hard | $Q(1,1,1)$ | integrated out in matching |
| $n$-collinear | $Q(\lambda^2,1,\lambda)$ | jet along $n$ |
| $\bar n$-collinear | $Q(1,\lambda^2,\lambda)$ | jet along $\bar n$ |
| ultrasoft | $Q(\lambda^2,\lambda^2,\lambda^2)$ | SCET$_\text{I}$ |
| soft | $Q(\lambda,\lambda,\lambda)$ | SCET$_\text{II}$ and many transverse-momentum observables |

The labels SCET$_\text{I}$ and SCET$_\text{II}$ refer to different mode hierarchies, not different physical laws.

## Collinear fields

A QCD quark field is decomposed into large and small spinor components relative to $n$ and $\bar n$. The large collinear quark field is denoted $\xi_n$ and satisfies a light-cone projection condition, conventionally written

$$
n\!\!\!/\,\xi_n=0.
$$

The leading collinear quark Lagrangian is

$$
\mathcal L_{\xi}^{(0)}
=\bar\xi_n
\left(
 i n\cdot D_n
+iD\!\!\!/_{n\perp}\frac{1}{i\bar n\cdot D_n}iD\!\!\!/_{n\perp}
\right)
\frac{\bar n\!\!\!/}{2}\xi_n,
$$

where $D_n$ is the collinear covariant derivative. This expression is nonlocal along the $\bar n$ direction because the small spinor component has been integrated out. That nonlocality is not acausal; it is the light-cone remnant of eliminating off-shell components inside an EFT expansion.

Collinear gauge invariance is encoded by Wilson lines such as

$$
W_n(x)=\operatorname P\exp\left[
ig\int_{-\infty}^0 ds\,\bar n\cdot A_n(x+s\bar n)
\right].
$$

A useful gauge-invariant building block is

$$
\chi_n=W_n^\dagger\xi_n.
$$

For gluons, one uses building blocks such as

$$
\mathcal B_{n\perp}^\mu
=\frac{1}{g}W_n^\dagger iD_{n\perp}^\mu W_n,
$$

up to normalization conventions. These building blocks make operator construction systematic.

## Soft Wilson lines and eikonal physics

Soft radiation sees an energetic particle primarily through its direction and color charge. At leading power, repeated soft emissions exponentiate into Wilson lines along the particle trajectory:

$$
Y_n(x)=\operatorname P\exp\left[
ig\int_{-\infty}^0 ds\,n\cdot A_s(x+sn)
\right].
$$

A field redefinition, often called the BPS field redefinition, decouples ultrasoft gluons from the leading collinear Lagrangian:

$$
\xi_n(x)=Y_n(x)\xi_n^{(0)}(x),
\qquad
A_n^\mu(x)=Y_n(x)A_n^{(0)\mu}(x)Y_n^\dagger(x).
$$

After this step, soft physics appears in external operators and soft functions rather than as arbitrary soft-collinear interactions in the leading Lagrangian. This is the structural reason factorization theorems become transparent in SCET.

## Matching QCD currents

A simple two-jet current in QCD has the form

$$
J(x)=\bar q(x)\Gamma q(x).
$$

After matching onto SCET at the hard scale $Q$, it becomes schematically

$$
J(x)\to C(Q,\mu)\,\bar\chi_{\bar n}(x)\Gamma_{\text{SCET}}\chi_n(x)+O(\lambda).
$$

The Wilson coefficient $C(Q,\mu)$ contains hard virtual corrections. The SCET matrix element contains collinear and soft dynamics. Squared amplitudes then produce hard functions such as

$$
H(Q,\mu)=|C(Q,\mu)|^2.
$$

The EFT does not make the calculation magically shorter at fixed order. Its power is that it separates scales and turns logarithmic structure into anomalous dimensions.

## Factorization

For an event-shape observable such as thrust in the two-jet limit, the factorized structure has the schematic form

$$
\frac{d\sigma}{d\tau}
=H(Q,\mu)
\int ds_n\,ds_{\bar n}\,dk\,
J_n(s_n,\mu)J_{\bar n}(s_{\bar n},\mu)S(k,\mu)
\delta\left(\tau-\frac{s_n+s_{\bar n}}{Q^2}-\frac{k}{Q}\right)
+\cdots.
$$

Here $\tau$ measures the departure from the perfect two-jet limit. The functions have distinct natural scales:

$$
\mu_H\sim Q,
\qquad
\mu_J\sim Q\lambda,
\qquad
\mu_S\sim Q\lambda^2.
$$

Computing all functions at one common scale produces large logarithms. Computing each at its natural scale and evolving them to a common scale resums those logarithms.

:::tip[Factorization is a statement with assumptions]
A factorization formula is not just a pretty product. It encodes a measurement definition, a power expansion, mode content, Wilson-line structure, subtraction of overlap regions, and assumptions about Glauber exchange or its cancellation.
:::

## RG evolution and Sudakov logarithms

The hard coefficient obeys an RG equation of the form

$$
\mu\frac{d}{d\mu}C(Q,\mu)
=\gamma_C(Q,\mu)C(Q,\mu).
$$

For massless gauge theories, anomalous dimensions often contain a cusp term:

$$
\gamma_C(Q,\mu)
=\Gamma_{\text{cusp}}(\alpha_s)\log\frac{Q^2}{\mu^2}+\gamma(\alpha_s).
$$

Solving this equation exponentiates Sudakov logarithms. The same cusp anomalous dimension appears in many Wilson-line problems because it measures the ultraviolet divergence associated with a cusp in a lightlike Wilson contour.

The practical resummation workflow is:

1. match QCD onto SCET at $\mu_H\sim Q$;
2. compute hard, jet, and soft functions at their natural scales;
3. evolve them with their anomalous dimensions;
4. convolve them according to the measurement function;
5. match to fixed-order QCD if the observable requires uniform accuracy away from the singular limit.

## SCET I and SCET II

SCET$_\text{I}$ describes problems where collinear modes have virtuality $Q^2\lambda^2$ while ultrasoft modes have much smaller virtuality $Q^2\lambda^4$. Examples include many inclusive endpoint and event-shape problems.

SCET$_\text{II}$ describes problems where soft and collinear modes have the same invariant mass scaling but different rapidities. Transverse-momentum dependent observables are typical examples. In this case ordinary dimensional regularization does not separate all divergences. One encounters **rapidity divergences** and needs a rapidity regulator and a rapidity RG.

The moral is simple: invariant mass is not the only scale. Modes can have the same virtuality and still be distinct because they live at different rapidities.

## Zero-bin subtraction and overlap

Since soft momenta can look like limits of collinear momenta, SCET must avoid double counting. The zero-bin subtraction removes the soft limit of a collinear integral. Schematically,

$$
I_{\text{collinear, subtracted}}
=I_{\text{collinear}}-I_{\text{zero-bin}}.
$$

In many modern formulations this subtraction is expressed through regulator choices, rapidity renormalization, or equivalent overlap-subtraction prescriptions. The conceptual point is invariant: factorization requires each mode to count a region of momentum space once.

## Worked example: why collinear virtuality is small

Let

$$
p^\mu\sim Q(\lambda^2,1,\lambda),
$$

with components $(n\cdot p,\bar n\cdot p,p_\perp)$. Then

$$
p^2=(n\cdot p)(\bar n\cdot p)+p_\perp^2.
$$

The first term scales as

$$
(n\cdot p)(\bar n\cdot p)\\sim (Q\lambda^2)(Q)=Q^2\lambda^2.
$$

The transverse term scales as

$$
p_\perp^2\sim Q^2\lambda^2.
$$

Therefore

$$
p^2\sim Q^2\lambda^2\ll Q^2.
$$

A collinear particle can carry energy of order $Q$ while still having small invariant mass. This is why jets are energetic but nearly lightlike.

## Common pitfalls

**Thinking soft means low energy and collinear means high energy, full stop.** A collinear mode has one large light-cone component, one small component, and a transverse component in between. A soft mode has all components small. The distinction is directional and scaling-based, not just energetic.

**Forgetting Wilson lines.** Wilson lines are not optional decoration. They are the gauge-invariant memory of energetic particles interacting with gauge fields.

**Calling every product formula factorization.** A factorization theorem requires a mode analysis, operator definitions, overlap subtraction, and an argument that omitted modes either cancel or are power suppressed.

**Ignoring rapidity divergences.** In SCET$_\text{II}$, soft and collinear modes can share the same virtuality. Rapidity regularization is then part of the EFT definition, not a cosmetic choice.

**Using SCET only as a resummation machine.** Resummation is one payoff, but SCET also organizes power corrections, helicity operators, subleading soft theorems, jet substructure, heavy-to-light decays, and factorization proofs.

**Confusing labels with physical particles.** The labels $n$ and $\bar n$ denote sectors in an expansion. Physical particles are not born with immutable labels; the labels are a bookkeeping device tied to the observable and kinematic region.

## Relations to other pages

SCET is often combined with other EFTs. In heavy-to-light decays, it works with HQET. In quarkonium production near endpoint regions, it can combine with NRQCD. In transverse-momentum observables, it overlaps with factorization and rapidity-RG technology. In collider physics, it provides the EFT backbone behind many precision resummations.

| Neighbor | Relation |
|---|---|
| [HQET](/renormalization-rg-eft/major-efts/heavy-quark-effective-theory/) | heavy quark plus energetic light particles in heavy-to-light decays |
| [NRQCD](/renormalization-rg-eft/major-efts/nonrelativistic-qcd/) | heavy quarkonium plus energetic radiation in endpoint or production problems |
| [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) | SCET resummation is multi-scale EFT running in action |
| [Matching with Background Fields](/renormalization-rg-eft/matching-running-decoupling/matching-with-background-fields/) | Wilson-line operators are naturally derived with background-field reasoning |
| Gauge theory factorization | SCET gives a gauge-invariant operator language for soft and collinear limits |

## Research status

SCET is an established framework for factorization and resummation. Leading-power factorization for many classic observables is mature, and the EFT has become standard in precision collider theory, $B$ physics, jet physics, and perturbative QCD resummation.

Active work includes subleading-power factorization, endpoint singularities, Glauber modes, rapidity RG schemes, non-global logarithms, multi-differential measurements, jet substructure, medium interactions, and the interface between SCET and parton showers. These are not signs that the basic EFT is shaky; they are signs that real observables are gloriously multiscale little gremlins.

## Exercises

### Exercise 1: Scaling of a collinear propagator

For an $n$-collinear momentum $p\sim Q(\lambda^2,1,\lambda)$, show that a massless propagator scales as $1/(Q^2\lambda^2)$.

<details><summary><strong>Solution</strong></summary>

The invariant mass is

$$
p^2=(n\cdot p)(\bar n\cdot p)+p_\perp^2\sim Q^2\lambda^2.
$$

Therefore the massless propagator scales as

$$
\frac{i}{p^2+i\epsilon}\sim \frac{1}{Q^2\lambda^2}.
$$

This enhancement relative to a hard propagator $1/Q^2$ is why collinear modes must remain explicit in the EFT.

</details>

### Exercise 2: Natural scales in a two-jet observable

Suppose a two-jet event shape has $\tau\ll 1$ and the jet invariant masses scale as $s_J\sim Q^2\tau$. Identify $\lambda$ and the natural hard, jet, and soft scales in SCET$_\text{I}$.

<details><summary><strong>Solution</strong></summary>

Since collinear virtuality scales as

$$
p_c^2\sim Q^2\lambda^2,
$$

and the jet invariant mass is $s_J\sim Q^2\tau$, we identify

$$
\lambda^2\sim \tau,
\qquad
\lambda\sim \sqrt\tau.
$$

The natural hard scale is

$$
\mu_H\sim Q.
$$

The jet scale is

$$
\mu_J\sim Q\lambda\sim Q\sqrt\tau.
$$

The ultrasoft scale is

$$
\mu_S\sim Q\lambda^2\sim Q\tau.
$$

Large logarithms of $\tau$ are resummed by evolving between these scales.

</details>

### Exercise 3: Wilson-line origin of eikonal emission

A soft gluon of momentum $k$ emitted from an energetic particle with momentum $p$ gives an eikonal denominator proportional to $1/(p\cdot k)$. Explain why this depends only on the direction of $p$ at leading power.

<details><summary><strong>Solution</strong></summary>

For an energetic particle moving close to the $n$ direction, write

$$
p^\mu\simeq \frac{\bar n\cdot p}{2}n^\mu.
$$

Then

$$
p\cdot k\simeq \frac{\bar n\cdot p}{2}n\cdot k.
$$

The numerator of the eikonal vertex also contains the large momentum direction. The overall large energy factor cancels between numerator and denominator, leaving a leading soft-emission factor controlled by the lightlike direction $n$ and the color charge. Repeated emissions exponentiate into a Wilson line along $n$.

</details>

## References

- C. W. Bauer, S. Fleming, D. Pirjol, and I. W. Stewart, foundational papers on soft-collinear effective theory.
- C. W. Bauer and I. W. Stewart, early work on invariant operators and power counting in SCET.
- M. Beneke, A. P. Chapovsky, M. Diehl, and T. Feldmann, work on soft-collinear factorization and power counting.
- T. Becher and M. Neubert, reviews and applications of SCET to collider and flavor physics.
- I. W. Stewart, lecture notes on SCET, factorization, and resummation.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on QCD, factorization, and jets.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on matching, power counting, and hierarchy logic.

## Version history

- 2026-06-19: First polished draft. Introduced light-cone scaling, collinear and soft modes, Wilson lines, matching, factorization, RG evolution, rapidity issues, and relation to HQET and NRQCD.
