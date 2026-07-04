---
title: "SCET Preview"
description: "A first guide to soft-collinear effective theory: modes, power counting, Wilson lines, matching, factorization, and resummation for infrared-sensitive observables."
sidebar:
  label: "SCET Preview"
  order: 11
level: Advanced
status: "Polished draft"
source: "Bauer–Fleming–Luke–Pirjol–Stewart on SCET; Beneke–Smirnov on regions; Manohar–Stewart; Becher–Neubert; Schwartz ch. 36"
topics:
  - soft-collinear effective theory
  - infrared factorization
  - Wilson lines
  - power counting
  - matching
  - resummation
canonicalTopics:
  - scet-preview
  - soft-collinear-effective-theory
  - effective-theory-factorization
  - infrared-mode-separation
researchStatus:
  established:
    - "SCET provides a systematic effective-field-theory framework for many observables controlled by hard, collinear, and soft momentum regions."
  active:
    - "Subleading-power factorization, Glauber exchange, rapidity evolution, non-global measurements, multi-jet observables, and hadron-collider power corrections remain active research areas."
---

## Summary

**Soft-collinear effective theory** (SCET) is the effective field theory for processes containing energetic particles in narrow directions together with much softer radiation. It is the EFT language behind many factorization and resummation formulas in perturbative QCD.

The basic hierarchy is

$$
Q \gg Q\lambda \gg Q\lambda^2,
\qquad \lambda\ll1,
$$

where $Q$ is a hard scale and $\lambda$ is a small expansion parameter set by the observable. Collinear modes carry large momentum along a lightlike direction and small invariant mass; soft or ultrasoft modes carry much smaller components. Hard fluctuations are integrated out and appear as Wilson coefficients.

A typical SCET matching statement has the schematic form

$$
J_{\rm QCD}
=\sum_i C_i(Q,\mu)\,O_i^{\rm SCET}(\mu),
$$

where $J_{\rm QCD}$ is a short-distance current or operator, $C_i$ contains hard virtual effects, and $O_i^{\rm SCET}$ contains collinear and soft fields. The same logic underlies factorization formulas such as

$$
\frac{d\sigma}{de}
=H(Q,\mu)
\int de_n\,de_{\bar n}\,de_s\,
J_n(e_n,\mu)J_{\bar n}(e_{\bar n},\mu)S(e_s,\mu)
\delta(e-e_n-e_{\bar n}-e_s)
+\text{power corrections}.
$$

SCET is not just notation for known factorization formulas. It gives a controlled expansion, operator definitions, symmetry constraints, anomalous dimensions, and a clean way to resum large logarithms. It also makes clear where factorization can fail or need refinement.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![SCET separates a hard interaction, collinear sectors, and soft Wilson-line interactions](/figures/perturbative-qft/scet-preview.svg)

<figcaption>

SCET separates a hard interaction at scale $Q$ from collinear sectors along lightlike directions and soft radiation that couples coherently through Wilson lines. Hard virtual modes become matching coefficients. Collinear and soft modes remain dynamical and are organized by a power expansion in $\lambda$.

</figcaption>
</figure>

## Prerequisites

You should know [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/), [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/), [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/), and [Resummation Preview](/perturbative-qft/infrared-physics-factorization/resummation-preview/).

For the QFT tools, review [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), [Wilson lines and gauge fields from the Foundations pages](/foundations/gauge-fields-first-principles/gauge-redundancy/), and [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/).

## Core idea

SCET is built from a simple observation. In many high-energy processes, the final state is not uniformly energetic in all directions. Instead, the event contains a few narrow energetic jets plus low-energy radiation connecting them.

A fixed-order loop or phase-space integral then contains several momentum regions:

```txt
hard:       virtuality of order Q²;
collinear:  large energy but small invariant mass;
soft:       small momentum, wide angle;
ultrasoft:  even softer, depending on the observable.
```

Each region has its own natural variables and its own logarithms. Trying to describe all of them with one expansion scale is like using a single ruler to measure both a cathedral and the dust on its windowsill. Technically legal, emotionally criminal.

SCET replaces the single QCD field description by fields adapted to the relevant momentum regions. Hard modes are removed by matching. Collinear fields describe energetic particles near lightlike directions. Soft fields describe long-wavelength radiation. Gauge invariance forces Wilson lines to appear, and those Wilson lines are exactly the eikonal objects that appeared earlier in soft limits.

The power of SCET is that it turns a momentum-region argument into an effective Lagrangian and operator expansion.

## Setup and conventions

We use qft.org scattering and gauge-theory conventions. This page only adds light-cone notation and the SCET power-counting parameter $\lambda$.

For a lightlike jet direction $n^\mu$, introduce another lightlike vector $\bar n^\mu$ such that

$$
n^2=0,
\qquad
\bar n^2=0,
\qquad
n\cdot\bar n=2.
$$

Any momentum can be decomposed as

$$
p^\mu
=\frac{\bar n\cdot p}{2}n^\mu
+\frac{n\cdot p}{2}\bar n^\mu
+p_\perp^\mu.
$$

In this page the ordered tuple

$$
(n\cdot p,\,\bar n\cdot p,\,p_\perp)
$$

records the small, large, and transverse components of an $n$-collinear momentum. With that convention an $n$-collinear mode scales as

$$
p_n^\mu\sim Q(\lambda^2,1,\lambda),
\qquad
p_n^2\sim Q^2\lambda^2.
$$

This is the convention-dependent place to pay attention. Some sources order the tuple as $(\bar n\cdot p,n\cdot p,p_\perp)$ instead. The physics is the same; the bookkeeping order is not.

## Modes and power counting

The mode content depends on the observable. The most common first distinction is between SCET I and SCET II.

| Theory | Collinear scaling $(n\cdot p,\bar n\cdot p,p_\perp)$ | Soft scaling | Typical situation |
|---|---:|---:|---|
| SCET I | $Q(\lambda^2,1,\lambda)$ | ultrasoft $Q(\lambda^2,\lambda^2,\lambda^2)$ | jet invariant masses much larger than soft virtuality |
| SCET II | $Q(\lambda^2,1,\lambda)$ | soft $Q(\lambda,\lambda,\lambda)$ | soft and collinear modes have comparable invariant mass |

In SCET I, the ultrasoft virtuality is

$$
p_{\rm us}^2\sim Q^2\lambda^4,
$$

while the collinear virtuality is $Q^2\lambda^2$. This hierarchy appears in many event shapes near the two-jet limit.

In SCET II, soft and collinear virtualities can be parametrically the same. This happens in transverse-momentum dependent factorization and endpoint observables. Rapidity divergences then become central: dimensional regularization controls invariant mass, but it does not by itself separate modes with the same invariant mass and different rapidity.

Power counting means assigning a scaling in $\lambda$ to momenta, fields, operators, and measurements. The EFT expansion is then an ordered series:

$$
\mathcal L_{\rm SCET}
=\mathcal L^{(0)}+\mathcal L^{(1)}+\mathcal L^{(2)}+\cdots,
\qquad
\mathcal L^{(k)}\sim \lambda^k.
$$

At leading power, the theory captures the singular terms in the infrared limit. Subleading powers describe power corrections.

## Matching: hard physics becomes Wilson coefficients

SCET does not try to reproduce hard virtual momenta dynamically. Instead, those modes are integrated out. Their effects are encoded in Wilson coefficients.

For example, a QCD current creating two energetic back-to-back jets has the leading-power matching form

$$
\bar\psi\Gamma\psi
\longrightarrow
C(Q,\mu)\,\bar\chi_{\bar n}\Gamma\chi_n
+O(\lambda),
$$

where $\chi_n$ and $\chi_{\bar n}$ are gauge-invariant collinear building blocks in the two lightlike directions. The coefficient $C(Q,\mu)$ is determined by matching QCD and SCET matrix elements at the hard scale. It contains only short-distance physics.

Matching is usually performed by computing the same on-shell or off-shell partonic matrix element in the full theory and in the EFT, using the same infrared regulator. Since the two theories have the same infrared behavior, the difference is short-distance and determines $C$.

At one loop this often looks like

$$
C(Q,\mu)
=1+\frac{\alpha_s(\mu)}{4\pi}
\left[-\Gamma_0\ln^2\frac{Q}{\mu}+\gamma_0\ln\frac{Q}{\mu}+c_1\right]
+\cdots,
$$

with coefficients fixed by the specific current and process. The double logarithm is a warning from the hard scale: if $\mu$ is far from $Q$, use RG evolution rather than fixed-order stubbornness.

## Wilson lines and gauge-invariant building blocks

Collinear gauge invariance is not optional. The useful collinear quark building block is

$$
\chi_n(x)=W_n^\dagger(x)\xi_n(x),
$$

where $\xi_n$ is an $n$-collinear quark field and $W_n$ is a collinear Wilson line. Schematically,

$$
W_n(x)
=\operatorname P\exp\left[ig\int_{-\infty}^0 ds\,
\bar n\cdot A_n(x+s\bar n)\right].
$$

The precise boundary prescription depends on the process and on whether fields are incoming or outgoing. The important point is structural: collinear gauge invariance dresses the collinear field with a Wilson line along the conjugate light-cone direction.

Soft gluons couple to energetic particles through eikonal interactions. At leading power, these interactions can be collected into soft Wilson lines such as

$$
Y_n(x)
=\operatorname P\exp\left[ig\int_{-\infty}^0 ds\,
 n\cdot A_s(x+sn)\right].
$$

After a suitable field redefinition, often called the BPS field redefinition, leading-power soft interactions are removed from the collinear Lagrangian and moved into the operators. This is the EFT origin of the soft function in many factorization theorems.

## Leading Lagrangian and decoupling

The leading collinear-quark Lagrangian has the schematic structure

$$
\mathcal L_{\xi}^{(0)}
=
\bar\xi_n
\left(
 i n\cdot D
+iD\!\!\!/_{\perp}
\frac{1}{i\bar n\cdot D}
iD\!\!\!/_{\perp}
\right)
\frac{\bar n\!\!\!/}{2}\xi_n,
$$

where $D\!\!\!/_{\perp}=\gamma_\perp^\mu D_{\perp\mu}$ and $\bar n\!\!\!/ =\gamma^\mu\bar n_\mu$. The inverse derivative should be understood in the EFT sense, acting on large label momenta and collinear residual dependence according to the chosen formalism.

The details of this Lagrangian are less important on a first pass than its implications:

1. collinear fields retain their own gauge interactions;
2. soft interactions simplify at leading power;
3. the expansion parameter $\lambda$ organizes all corrections;
4. hard dynamics appears only through matching coefficients.

The decoupling of soft and collinear dynamics at leading power is what makes factorization possible. It is not a statement that soft radiation is physically absent. It is a statement that its leading interactions are universal and can be isolated into Wilson-line matrix elements.

## Factorization in EFT language

A factorization theorem becomes a statement about matching and matrix elements.

For a two-jet event-shape variable $e$ in $e^+e^-$ annihilation near the dijet limit, the structure is schematically

$$
\frac{d\sigma}{de}
=
H(Q,\mu)
\int de_n\,de_{\bar n}\,de_s\,
J_n(e_n,\mu)
J_{\bar n}(e_{\bar n},\mu)
S(e_s,\mu)
\delta(e-e_n-e_{\bar n}-e_s)
+\text{power corrections}.
$$

The factors have different meanings:

| Factor | EFT origin | Sensitive to |
|---|---|---|
| $H$ | squared hard matching coefficient | virtual momenta of order $Q$ |
| $J_n$, $J_{\bar n}$ | collinear matrix elements | energetic radiation inside jets |
| $S$ | soft Wilson-line matrix element | low-energy wide-angle radiation |
| power corrections | subleading SCET operators and Lagrangians | corrections suppressed by $\lambda$ |

This formula is intentionally schematic. Real observables require precise measurement functions, plus distributions, color matrices, rapidity regulators when needed, and sometimes hadronic matrix elements such as PDFs or fragmentation functions.

The conceptual lesson is robust: factorization is an operator statement in an EFT, not just a clever way to name pieces of an integral.

## Resummation from SCET

The pieces in a factorization theorem depend on the renormalization scale $\mu$, but the physical cross section does not. For a multiplicative toy factorization formula,

$$
\sigma=H(Q,\mu)J(Q\lambda,\mu)S(Q\lambda^2,\mu),
$$

RG invariance implies

$$
\gamma_H+\gamma_J+\gamma_S=0,
$$

with the appropriate convolution or matrix generalization in realistic cases.

Each function is evaluated most naturally at its own scale:

$$
\mu_H\sim Q,
\qquad
\mu_J\sim Q\lambda,
\qquad
\mu_S\sim Q\lambda^2.
$$

Then RG evolution moves the functions to a common scale:

$$
\sigma
=H(Q,\mu_H)
U_H(\mu_H,\mu)
J(\mu_J)U_J(\mu_J,\mu)
S(\mu_S)U_S(\mu_S,\mu).
$$

This is the SCET route to Sudakov resummation. The cusp anomalous dimension controls the universal part of many double logarithms. Non-cusp anomalous dimensions and matching constants depend on the process and observable.

## SCET I versus SCET II

The difference between SCET I and SCET II is not academic pedantry. It changes the regulatory and factorization structure.

In SCET I, collinear and ultrasoft modes have different invariant masses. Ordinary dimensional regularization often separates the UV and IR structure cleanly enough for many calculations. Event shapes near the two-jet limit are typical examples.

In SCET II, soft and collinear modes can have the same invariant mass but different rapidity. Then loop integrals may contain rapidity divergences: divergences associated with boosts along the light cone rather than with invariant momentum size. One introduces a rapidity regulator and a rapidity scale, often denoted $\nu$, in addition to $\mu$.

The result is a two-scale evolution structure:

$$
\mu\frac{d}{d\mu}F=\gamma_\mu F,
\qquad
\nu\frac{d}{d\nu}F=\gamma_\nu F.
$$

This is essential in transverse-momentum dependent factorization and related problems. It is also where several factorization subtleties live.

## A minimal example: endpoint logarithms

Suppose an observable constrains radiation to have invariant mass much smaller than $Q^2$. In full QCD, a loop or real-emission calculation produces logarithms such as

$$
\ln\frac{m_J^2}{Q^2},
\qquad
m_J^2\ll Q^2.
$$

In SCET, the hard scale $Q$ is removed by matching, while the small jet scale appears in the matrix element of a jet operator. Instead of one expression containing both scales, the calculation separates into

$$
\text{hard coefficient at }Q
\quad\times\quad
\text{jet matrix element at }m_J
\quad\times\quad
\text{soft matrix element if needed}.
$$

The large logarithm becomes an RG evolution logarithm between natural scales. This is the EFT way of saying: do not ask one perturbative expansion to do three scale jobs at once.

## What SCET does not automatically solve

SCET gives a framework, not a magic wand.

A factorization theorem still requires proof or careful evidence. One must specify the observable, the mode content, the regulator, the operator basis, the treatment of Glauber exchange, the measurement function, and the power-counting limit.

For hadron collisions, additional complications enter:

```txt
initial-state collinear sectors;
parton distribution functions;
beam functions;
Glauber gluons;
color mixing among many hard directions;
rapidity logarithms;
non-global measurements;
underlying event and hadronization corrections.
```

SCET is best understood as a sharp language for separating and testing these ingredients. It makes the assumptions visible.

## Common pitfalls

**Treating SCET as just a diagram trick.** SCET is an EFT with fields, operators, matching coefficients, symmetries, power counting, and RG evolution. Diagrams are only one way to compute inside it.

**Confusing soft with ultrasoft.** The word “soft” is used differently in different SCET settings. Always state the momentum scaling.

**Forgetting rapidity divergences.** In SCET II, dimensional regularization alone may not separate soft and collinear modes. A rapidity regulator and rapidity evolution may be required.

**Assuming factorization without checking the observable.** Not every measurement factorizes into hard, jet, and soft functions. Non-global constraints, Glauber exchange, and recoil sensitivity can change the story.

**Thinking Wilson lines are optional decorations.** Wilson lines are forced by gauge invariance and by the leading eikonal coupling of soft radiation to energetic particles.

**Overstating leading-power results.** Leading-power SCET captures singular terms in a limit. Precision predictions often require subleading-power corrections, fixed-order matching, and nonperturbative inputs.

## Relations to other pages

- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) identify the singular regions SCET organizes.
- [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/) gives the leading soft coupling that becomes a Wilson line.
- [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) is the amplitude-level ancestor of the Wilson-line soft function.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) explains the hard–jet–soft decomposition before EFT formalism.
- [Resummation Preview](/perturbative-qft/infrared-physics-factorization/resummation-preview/) explains how anomalous dimensions sum large logarithms.
- [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) explains the observable side of jet physics.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) and [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/) provide the RG language.

## Research status

- **Established:** Leading-power SCET factorization and RG evolution are standard tools for many event shapes, inclusive decays, endpoint spectra, jet observables, transverse-momentum observables, and collider precision calculations.
- **Active:** Subleading-power factorization, Glauber regions, non-global logarithms, rapidity factorization, multi-differential measurements, jet grooming, and robust uncertainty estimates remain active areas.
- **Speculative:** SCET itself is not speculative. Some proposed factorization formulas or all-orders treatments for difficult observables may be conjectural or proven only under restricted assumptions.

## Exercises

### Exercise 1: Collinear virtuality

Using the scaling

$$
(n\cdot p,\bar n\cdot p,p_\perp)\sim Q(\lambda^2,1,\lambda),
$$

show that an $n$-collinear momentum has invariant mass $p^2\sim Q^2\lambda^2$.

<details>
<summary><strong>Solution</strong></summary>

Using the light-cone decomposition,

$$
p^2=(n\cdot p)(\bar n\cdot p)+p_\perp^2,
$$

up to the sign convention for the transverse square. In mostly-minus signature, $p_\perp^2$ is negative for an ordinary spatial transverse momentum, but its magnitude scales as $Q^2\lambda^2$.

The first term scales as

$$
(n\cdot p)(\bar n\cdot p)
\sim
(Q\lambda^2)(Q)=Q^2\lambda^2,
$$

and the transverse term has magnitude

$$
|p_\perp^2|\sim Q^2\lambda^2.
$$

Therefore

$$
p^2\sim Q^2\lambda^2.
$$

</details>

### Exercise 2: Eikonal denominator from soft emission

Let an energetic massless particle with momentum $p$ emit a soft momentum $k$. Show that the internal propagator denominator satisfies

$$
(p+k)^2+i\epsilon\simeq 2p\cdot k+i\epsilon
$$

at leading power.

<details>
<summary><strong>Solution</strong></summary>

Expand the denominator:

$$
(p+k)^2=p^2+2p\cdot k+k^2.
$$

For a massless external energetic particle, $p^2=0$. In the soft limit, $k$ is parametrically smaller than $p$, so $k^2$ is suppressed compared with $2p\cdot k$. Thus

$$
(p+k)^2+i\epsilon
=2p\cdot k+k^2+i\epsilon
\simeq 2p\cdot k+i\epsilon.
$$

This is the denominator that leads to eikonal soft factors and, after exponentiation, Wilson lines.

</details>

### Exercise 3: RG consistency of a factorized observable

Suppose a multiplicative leading-power factorization formula has the form

$$
\sigma=H(Q,\mu)J(\mu)S(\mu),
$$

and each factor satisfies

$$
\mu\frac{d}{d\mu}F(\mu)=\gamma_F(\mu)F(\mu).
$$

Show that RG invariance of $\sigma$ implies $\gamma_H+\gamma_J+\gamma_S=0$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate the factorized cross section:

$$
\mu\frac{d\sigma}{d\mu}
=\left(\gamma_H+\gamma_J+\gamma_S\right)HJS.
$$

A physical cross section cannot depend on the arbitrary scale $\mu$, so

$$
\mu\frac{d\sigma}{d\mu}=0.
$$

Assuming $HJS$ is nonzero, this gives

$$
\gamma_H+\gamma_J+\gamma_S=0.
$$

For realistic observables the products may be convolutions and the anomalous dimensions may be matrices or distributions, but the consistency condition is the same idea.

</details>

### Exercise 4: Natural scales

For a two-jet event shape with $e\sim\lambda^2$, identify the natural hard, jet, and soft scales in SCET I.

<details>
<summary><strong>Solution</strong></summary>

The hard scale is set by the total energy,

$$
\mu_H\sim Q.
$$

The collinear invariant mass scales as

$$
p_c^2\sim Q^2\lambda^2.
$$

Therefore the jet scale is

$$
\mu_J\sim Q\lambda.
$$

In SCET I the ultrasoft momentum scales as $Q\lambda^2$, so the soft scale is

$$
\mu_S\sim Q\lambda^2.
$$

Since $e\sim\lambda^2$, this can also be written schematically as

$$
\mu_J\sim Q\sqrt e,
\qquad
\mu_S\sim Qe.
$$

</details>

## References

- C. W. Bauer, S. Fleming, and M. E. Luke, “Summing Sudakov logarithms in $B\to X_s\gamma$ in effective field theory,” *Physical Review D* **63** (2000), for the early SCET construction.
- C. W. Bauer, S. Fleming, D. Pirjol, and I. W. Stewart, “An effective field theory for collinear and soft gluons,” *Physical Review D* **63** (2001), for the canonical formulation of SCET modes and interactions.
- C. W. Bauer and I. W. Stewart, “Invariant operators in collinear effective theory,” *Physics Letters B* **516** (2001), for operator-building logic.
- C. W. Bauer, D. Pirjol, and I. W. Stewart, “Soft-collinear factorization in effective field theory,” *Physical Review D* **65** (2002), for the Wilson-line decoupling viewpoint.
- T. Becher, A. Broggio, and A. Ferroglia, *Introduction to Soft-Collinear Effective Theory*, for a modern pedagogical review.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 32, and 36, for infrared divergences, jets, factorization, and SCET.

## Version history

- **2026-06-13:** Initial QFT.org page. Added light-cone power counting, SCET I/II distinction, Wilson-line interpretation, leading-factorization structure, RG-resummation logic, and solved exercises.
