---
title: "Jets and Inclusive Observables"
description: "How infrared-safe measurement functions, jet algorithms, event shapes, and inclusive sums turn soft and collinear partons into finite physical observables."
sidebar:
  label: "Jets and Inclusive Observables"
  order: 8
level: Graduate
status: "Polished draft"
source: "Kinoshita–Lee–Nauenberg; Sterman on QCD and factorization; Ellis–Stirling–Webber; Catani–Seymour; Salam on jet algorithms; Schwartz chs. 20, 32, and 36"
topics:
  - jets
  - infrared safety
  - inclusive observables
  - event shapes
  - QCD factorization
canonicalTopics:
  - jets-and-inclusive-observables
  - infrared-safe-observables
  - jet-algorithms
  - measurement-functions
researchStatus:
  established:
    - "Infrared-safe observables are finite order by order in perturbative QCD after real and virtual soft and collinear singularities are combined, with initial-state collinear singularities absorbed into PDFs when needed."
  active:
    - "Precision jet physics requires resummation, nonperturbative corrections, pileup mitigation, grooming, non-global logarithms, and effective-theory factorization beyond the introductory fixed-order picture."
---

## Summary

Perturbative QCD does not predict a finite cross section for “exactly three partons and nothing else.” Massless gauge theories produce arbitrarily soft radiation and nearly collinear splittings. A physical observable must be inclusive enough that it cannot distinguish states related by unresolved soft or collinear emissions.

A final-state observable can be represented by measurement functions $F_n$ acting on $n$ final-state momenta:

$$
\sigma[F]
=
\sum_n\frac{1}{S_n}
\int d\Pi_n\,|\mathcal M_n|^2\,F_n(p_1,\ldots,p_n).
$$

For a massless final-state observable to be infrared and collinear safe, the measurement functions must satisfy the two limiting conditions

$$
F_{n+1}(p_1,\ldots,p_n,k)\longrightarrow F_n(p_1,\ldots,p_n)
\qquad (k\to0),
$$

and

$$
F_{n+1}(p_1,\ldots,zp,(1-z)p,\ldots,p_n)
\longrightarrow
F_n(p_1,\ldots,p,
\ldots,p_n)
$$

when two massless final-state momenta become collinear.

Jets are the practical bridge between partons and measurements. A jet algorithm clusters many hadrons, or many perturbative partons, into a smaller set of hard directions. If the observable and the algorithm are infrared and collinear safe, the perturbative calculation has a chance to describe a real detector-level measurement after controlled nonperturbative and experimental corrections.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Infrared-safe observables map hard partons, soft emissions, collinear splittings, and hadrons to the same measured quantity when the radiation is unresolved](/figures/perturbative-qft/jets-inclusive-observables.svg)

<figcaption>

An infrared-safe measurement is insensitive to unresolved soft emissions and collinear splittings. Jet algorithms and event shapes implement this idea in different ways: they replace microscopic particle multiplicity by stable macroscopic information such as energy flow, jet directions, jet masses, and angular correlations.

</figcaption>
</figure>

## Prerequisites

You should know [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/), [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/), [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/), and [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/).

## Core idea

The elementary quanta in a perturbative QCD calculation are quarks and gluons. The long-distance objects in a detector are hadrons. Neither description gives a unique particle-by-particle map.

A high-energy quark usually becomes a spray of hadrons. A gluon can split into two nearly collinear gluons, or into a nearly collinear quark-antiquark pair. Soft gluons can be emitted with arbitrarily low energy. If an observable changes violently under these unresolved operations, it is not a clean perturbative observable.

The useful object is not a fixed parton multiplicity. The useful object is a measurement that groups degenerate states together:

```txt
hard parton direction
  + soft radiation
  + collinear splittings
  + hadronization
  → measured jet or energy-flow observable.
```

This is the operational content of the KLN theorem in collider physics. The observable must sum over states that are experimentally and theoretically degenerate in the infrared.

## Setup and conventions

Consider a hard process with characteristic scale $Q$. In a final-state QCD calculation, perturbation theory generates terms with different numbers of real partons:

$$
2\to n,
\qquad
2\to n+1,
\qquad
2\to n+2,
\ldots
$$

Virtual corrections live at lower multiplicity, while real soft and collinear radiation lives at higher multiplicity. A physical prediction combines them with the same measurement prescription.

For a final-state measurement $F$, the schematic perturbative cross section is

$$
\sigma[F]
=
\sum_n\int d\Pi_n\,|\mathcal M_n|^2 F_n.
$$

The symbols hide spin sums, color sums, symmetry factors, flux factors, cuts, and renormalization. What matters here is that the same observable is evaluated on every possible final-state multiplicity.

For hadron collisions, initial-state collinear singularities do not simply cancel. They are absorbed into parton distribution functions. A schematic factorized hadron-collider prediction has the form

$$
d\sigma[F]
=
\sum_{a,b}f_{a/h_1}\otimes f_{b/h_2}\otimes d\widehat\sigma_{ab}[F].
$$

Final-state jets and event shapes then impose the measurement $F$ on the perturbative final state.

## Infrared and collinear safety

An observable is **infrared safe** if adding an infinitely soft particle does not change the measured value:

$$
F_{n+1}(p_1,\ldots,p_n,k)
\to
F_n(p_1,\ldots,p_n)
\quad\text{as}\quad k\to0.
$$

It is **collinear safe** if replacing one massless particle by two exactly collinear particles with the same total momentum does not change the measured value:

$$
F_{n+1}(\ldots,zp,(1-z)p,\ldots)
\to
F_n(\ldots,p,\ldots).
$$

Together these properties are often called **IRC safety**.

The reason these limits matter is local. Real-emission matrix elements have singular limits of the schematic form

$$
d\sigma_{n+1}^{\rm real}
\sim
 d\sigma_n^{\rm hard}
\times
\left[
\frac{d\omega}{\omega}
\quad\text{or}\quad
\frac{d\theta^2}{\theta^2}
\right].
$$

Virtual corrections contain matching singularities with opposite sign. If the measurement treats the unresolved real-emission configuration like the lower-multiplicity configuration, the cancellation can occur locally enough to leave a finite answer.

If the measurement vetoes all real radiation but keeps the virtual correction, the cancellation fails. That is the tiny gremlin behind many infrared disasters.

## Examples of safe and unsafe observables

| Observable | Infrared safe? | Collinear safe? | Comment |
|---|---:|---:|---|
| Total inclusive $e^+e^-\to$ hadrons rate | yes | yes | Fully inclusive final-state sum. |
| Thrust in $e^+e^-$ | yes | yes | Depends on total energy flow, not microscopic splitting. |
| Modern anti-$k_T$ jet cross section | yes | yes | With finite jet radius and finite cuts. |
| Exactly $n$ partons and no additional radiation | no | no | A fixed parton multiplicity is not a physical QCD observable. |
| Number of hadrons in an event | no | no | Sensitive to nonperturbative fragmentation and collinear splittings. |
| Energy in a calorimeter region with a hard threshold | usually yes | usually yes | Details matter near boundaries and thresholds. |

Being IRC safe does not mean the observable has no logarithms. It means the fixed-order coefficients are finite. If the observable imposes a small scale, such as a narrow jet mass or a small event-shape variable, perturbation theory may contain large logarithms that must be resummed.

## Event shapes

Event shapes are functions of the whole final-state energy flow. A classic example in $e^+e^-$ annihilation is thrust:

$$
T
=
\max_{\hat n}
\frac{\sum_i |\hat n\cdot\mathbf p_i|}{\sum_i |\mathbf p_i|},
\qquad
\tau=1-T.
$$

Two narrow back-to-back jets have $T\simeq1$, or $\tau\simeq0$. A spherical event has smaller $T$.

Thrust is IRC safe. Adding a soft particle changes the numerator and denominator by an amount proportional to its energy. Splitting a massless particle into two exactly collinear particles leaves the total momentum along every direction unchanged:

$$
|\hat n\cdot z\mathbf p|+|\hat n\cdot(1-z)\mathbf p|
=|\hat n\cdot\mathbf p|.
$$

That is the kind of measurement-level stability required for perturbative predictions.

## Jet algorithms

A jet algorithm maps a list of particles or partons to a list of jets. Modern collider jet algorithms are designed to be IRC safe.

The widely used sequential recombination family defines pair and beam distances

$$
d_{ij}
=
\min(p_{Ti}^{2p},p_{Tj}^{2p})\frac{\Delta R_{ij}^2}{R^2},
\qquad
 d_{iB}=p_{Ti}^{2p},
$$

where

$$
\Delta R_{ij}^2=(y_i-y_j)^2+(\phi_i-\phi_j)^2.
$$

The parameter $R$ is the jet radius, and the exponent $p$ defines common algorithms:

| Algorithm | $p$ | Typical behavior |
|---|---:|---|
| $k_T$ | $1$ | Clusters soft particles early; useful for substructure and theory. |
| Cambridge/Aachen | $0$ | Clusters by angle; useful for declustering. |
| anti-$k_T$ | $-1$ | Produces stable cone-like hard jets; standard at hadron colliders. |

The algorithm repeatedly clusters the smallest distance. If the smallest distance is $d_{ij}$, particles $i$ and $j$ are recombined. If it is $d_{iB}$, particle $i$ is declared a jet.

IRC safety means that adding an infinitely soft particle or splitting a particle collinearly does not change the hard jets except by adding soft momentum or recombining collinear fragments. Modern jet algorithms are built around exactly that requirement.

## Inclusive enough does not mean totally inclusive

“Inclusive” is not all or nothing. A total cross section is highly inclusive, but many useful measurements are only partially inclusive. A two-jet rate with a finite resolution parameter is not fully inclusive, but it can still be IRC safe because unresolved emissions are clustered or ignored in the right limits.

The sharp distinction is:

```txt
exclusive fixed particle content:
  usually IR unsafe;

exclusive with a finite resolution definition:
  can be IR safe;

inclusive over unresolved degenerate states:
  required for perturbative finiteness.
```

A measurement may be exclusive at the level of resolved jets while inclusive over unresolved particles inside those jets.

## Factorization viewpoint

For observables with several separated scales, IRC safety is only the beginning. A jet mass distribution, for example, may involve

$$
Q
\gg
m_J
\gg
\Lambda_{\rm QCD}.
$$

The cross section can contain large logarithms such as

$$
\log\frac{m_J^2}{Q^2}.
$$

A factorization theorem separates physics associated with hard, collinear, and soft modes. Schematically,

$$
d\sigma
\sim
H(Q,\mu)\otimes J(\text{collinear},\mu)\otimes S(\text{soft},\mu),
$$

and renormalization group evolution resums logarithms between the scales.

For hadron colliders, PDFs appear because initial-state collinear radiation is absorbed into universal hadron structure:

$$
d\sigma
\sim
f\otimes f\otimes H\otimes J\otimes S.
$$

The precise objects depend on the observable. The lesson is stable: a measured jet observable is finite because the measurement, factorization, and renormalization are designed to handle unresolved radiation systematically.

## Nonperturbative and experimental corrections

IRC safety means that perturbation theory is finite. It does not mean perturbation theory is exact.

A jet observable still receives corrections from

```txt
hadronization,
underlying event,
pileup,
detector response,
finite hadron masses,
nonperturbative soft radiation,
PDF uncertainties for hadron beams.
```

For sufficiently hard observables, many nonperturbative effects are suppressed by powers of $\Lambda_{\rm QCD}/Q$ or by powers involving jet masses and radii. But near endpoint regions, where an observable becomes sensitive to very small invariant masses or energies, nonperturbative shape functions or dedicated modeling may be needed.

This is not a defect of QCD. It is the ordinary price of asking a finite-resolution detector to measure a theory with massless partons and confining long-distance dynamics. The art is choosing observables where the price is calculable or controllable.

## Common pitfalls

**Equating partons with jets.** A jet is not a parton. A jet is a measurement-defined object built from many particles and compared to a perturbative calculation through an IRC-safe algorithm.

**Thinking finite means small.** IRC-safe observables have finite fixed-order coefficients, but they may contain large logarithms that require resummation.

**Forgetting initial-state collinear physics.** In hadron collisions, collinear radiation from incoming partons is absorbed into PDFs. It does not simply disappear by summing final states.

**Calling any cut “inclusive.”** A cut can ruin infrared safety if it distinguishes a soft or collinear emission from the unresolved configuration it approximates.

**Ignoring nonperturbative corrections.** IRC safety makes perturbation theory meaningful; it does not erase hadronization or detector effects.

## Relations to other pages

- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) introduces inclusive sums before the special complications of QCD jets.
- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) explain the singular limits that IRC safety must tame.
- [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) states the cancellation principle behind inclusive finite rates.
- [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) explains the non-Abelian soft factors entering QCD jet radiation.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) will turn the schematic $H\otimes J\otimes S$ structure into a systematic framework.
- [SCET Preview](/perturbative-qft/infrared-physics-factorization/scet-preview/) will introduce the effective field theory that makes many jet factorization theorems transparent.

## Research status

- **Established:** IRC safety, modern jet algorithms, event-shape calculations, and factorization for many standard observables are part of the mature perturbative QCD toolkit.
- **Active:** Jet substructure, grooming, non-global logarithms, transverse-momentum dependent factorization, precision event-shape fits, heavy-ion jets, and machine-learned observables are active research areas.
- **Speculative:** Proposed observables that are not manifestly IRC safe can still be useful experimentally, but they require additional nonperturbative modeling or new theoretical control before being treated as precision perturbative quantities.

## Exercises

### Exercise 1: Soft safety of thrust

Show that adding a particle of energy $\omega\ll Q$ changes thrust by at most order $\omega/Q$.

<details>
<summary><strong>Solution</strong></summary>

Thrust is

$$
T=\max_{\hat n}\frac{\sum_i|\hat n\cdot\mathbf p_i|}{\sum_i|\mathbf p_i|}.
$$

Adding a soft particle with momentum $\mathbf k$ changes the numerator by at most $|\mathbf k|=\omega$ for any axis $\hat n$. It changes the denominator by $\omega$. If the original hard energy is $Q=\sum_i|\mathbf p_i|$, the fractional change in the ratio is therefore at most of order

$$
\frac{\omega}{Q}.
$$

Thus the observable approaches its original value as $\omega\to0$.

</details>

### Exercise 2: Collinear safety of thrust

A massless particle with momentum $p$ splits into two exactly collinear particles with momenta $zp$ and $(1-z)p$. Show that thrust is unchanged.

<details>
<summary><strong>Solution</strong></summary>

For any thrust axis $\hat n$,

$$
|\hat n\cdot z\mathbf p|+|\hat n\cdot(1-z)\mathbf p|
=
z|\hat n\cdot\mathbf p|+(1-z)|\hat n\cdot\mathbf p|
=|\hat n\cdot\mathbf p|.
$$

The denominator is also unchanged:

$$
|z\mathbf p|+|(1-z)\mathbf p|=|\mathbf p|.
$$

Therefore the value of the thrust ratio for every axis is unchanged, and the maximizing value is unchanged as well.

</details>

### Exercise 3: Why exact parton multiplicity is unsafe

Explain why the statement “exactly two final-state partons” is not an infrared-safe observable in massless QCD.

<details>
<summary><strong>Solution</strong></summary>

The two-parton virtual correction contains soft and collinear singularities. These singularities are canceled by the real-emission contribution in which an additional gluon is soft or collinear to one of the hard partons.

If the observable demands exactly two final-state partons, it assigns

$$
F_2=1,
\qquad
F_3=0
$$

for the unresolved three-parton configuration. This violates the required soft and collinear limits

$$
F_3\to F_2.
$$

The real-emission singular region is removed instead of being combined with the virtual correction, so the cancellation fails.

</details>

### Exercise 4: An IRC-safe two-jet rate

Why can a two-jet rate with a finite jet-resolution parameter be infrared safe even though it is called “exclusive”?

<details>
<summary><strong>Solution</strong></summary>

The word “exclusive” here means exclusive in the number of resolved jets, not exclusive in the number of partons or hadrons. If an extra gluon is sufficiently soft or collinear, the jet algorithm either clusters it into an existing jet or treats it as unresolved. Therefore the measurement function obeys

$$
F_{n+1}\to F_n
$$

in unresolved limits. The observable can veto additional resolved jets while still summing inclusively over unresolved radiation. That is why it can be IRC safe.

</details>

## References

- T. Kinoshita, “Mass Singularities of Feynman Amplitudes,” *Journal of Mathematical Physics* **3** (1962), and T. D. Lee and M. Nauenberg, “Degenerate Systems and Mass Singularities,” *Physical Review* **133** (1964), for the KLN cancellation principle.
- G. Sterman, *An Introduction to Quantum Field Theory*, and Sterman's QCD factorization lectures, for infrared safety and factorization logic.
- R. K. Ellis, W. J. Stirling, and B. R. Webber, *QCD and Collider Physics*, for classic jet physics and perturbative QCD phenomenology.
- S. Catani and M. H. Seymour, “A General Algorithm for Calculating Jet Cross Sections in NLO QCD,” *Nuclear Physics B* **485** (1997), for subtraction and infrared-safe jet cross sections.
- G. P. Salam, “Towards Jetography,” *European Physical Journal C* **67** (2010), for a modern overview of jet algorithms.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 32, and 36, for infrared divergences, QCD radiation, jets, and SCET.

## Version history

- **2026-06-13:** Initial page. Emphasizes measurement functions, IRC safety, jet algorithms, event shapes, and the difference between resolved exclusivity and unsafe fixed multiplicity.
