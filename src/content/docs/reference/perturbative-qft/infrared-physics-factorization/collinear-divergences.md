---
title: "Collinear Divergences"
description: "How massless particles moving in nearly the same direction produce infrared singularities, how amplitudes factorize into splitting functions, and why jets, PDFs, and fragmentation functions are needed."
sidebar:
  label: "Collinear Divergences"
  order: 2
level: Graduate
status: "Polished draft"
source: "Altarelli–Parisi; DGLAP; Weinberg Vol. I on infrared effects; Srednicki §26; Schwartz chs. 20, 32, and 36"
topics:
  - infrared divergences
  - collinear factorization
  - splitting functions
  - jets
  - parton distributions
canonicalTopics:
  - collinear-divergences
  - collinear-factorization
  - splitting-functions
  - infrared-safe-jets
  - mass-singularities
researchStatus:
  established:
    - "Collinear factorization, universal leading splitting functions, mass singularities, jet safety, and PDF factorization are standard tools of perturbative gauge theory."
  active:
    - "Precision collider predictions still require increasingly refined treatments of collinear radiation, heavy-quark masses, endpoint regions, transverse-momentum dependence, Glauber effects, jet substructure, and factorization violations or limitations."
---

## Summary

A **collinear divergence** is an infrared singularity caused by massless particles moving in nearly the same direction. Unlike a soft divergence, the emitted particle need not have tiny energy. The singular limit is instead

$$
s_{ij}=2p_i\cdot p_j\to0,
$$

with both $p_i^2=p_j^2=0$ and $p_i$ nearly parallel to $p_j$.

In a massless gauge theory, the probability for a parent parton $a$ to split into nearly collinear daughters $b$ and $c$ has the universal leading form

$$
 dP_{a\to bc}
 =
 \frac{\alpha_s}{2\pi}
 P_{a\to bc}(z)\,dz\,
 \frac{d\mathbf k_\perp^2}{\mathbf k_\perp^2}
$$

up to convention-dependent spin and color averaging. Here $z$ is the longitudinal momentum fraction carried by one daughter and $\mathbf k_\perp$ is the relative transverse momentum. The logarithmic integral

$$
\int_0 \frac{d\mathbf k_\perp^2}{\mathbf k_\perp^2}
$$

is the collinear divergence.

Collinear divergences do not mean that massless gauge theory is unusable. They mean that observables must be insensitive to unresolved collinear splittings, or else the singularity must be absorbed into an appropriate long-distance object such as a parton distribution function, fragmentation function, or jet function.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![A massless parent line splits into two nearly parallel daughters; the singular region factorizes into a splitting function multiplying a lower-multiplicity hard process](/figures/perturbative-qft/collinear-divergences.svg)

<figcaption>

In the collinear limit, a nearly on-shell parent with momentum $P$ splits into two massless daughters with longitudinal fractions $z$ and $1-z$ and relative transverse momentum $\mathbf k_\perp$. The hard process cannot resolve the splitting at leading power, so the singular region factorizes into a universal splitting kernel times a lower-multiplicity amplitude or cross section.

</figcaption>
</figure>

## Prerequisites

You should know [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/), [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/), and [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/).

## Core idea

Collinear divergences are caused by a propagator becoming on shell when a massless particle splits into two particles moving in almost the same direction. The hard scattering sees only the total momentum of the narrow bundle. It cannot resolve whether that momentum was carried by one massless particle or by two nearly parallel massless particles.

The universal pattern is

```txt
hard process with parent a
        ×
collinear splitting a → b c.
```

At leading power, the singular collinear part does not depend on the detailed hard process. It depends only on the species, spin, color representation, longitudinal momentum fraction $z$, and transverse momentum scale $\mathbf k_\perp^2$ of the splitting.

This is why the same splitting functions appear in many places: final-state jets, initial-state parton evolution, fragmentation functions, parton showers, and soft-collinear effective theory.

## Setup and conventions

We use qft.org mostly-minus conventions and write

$$
s_{ij}=2p_i\cdot p_j=(p_i+p_j)^2
$$

for two massless daughter momenta. The collinear limit is

$$
p_i^\mu\parallel p_j^\mu,
\qquad
s_{ij}\to0.
$$

A useful parametrization introduces a lightlike parent direction $P^\mu$ and a transverse momentum $k_\perp^\mu$ satisfying

$$
P^2=0,
\qquad
P\cdot k_\perp=0.
$$

At leading power, the daughters can be written schematically as

$$
p_i^\mu\simeq zP^\mu+k_\perp^\mu+\text{small correction},
$$

$$
p_j^\mu\simeq (1-z)P^\mu-k_\perp^\mu+\text{small correction},
$$

with both daughters on shell. The invariant mass of the pair is then

$$
 s_{ij}
 \simeq
 \frac{\mathbf k_\perp^2}{z(1-z)}.
$$

The singular region is $\mathbf k_\perp^2\to0$ at fixed $0<z<1$. Endpoint limits such as $z\to1$ or $z\to0$ are soft-collinear regions and require care to avoid double counting.

## Why the propagator becomes singular

Suppose two nearly collinear massless daughters with momenta $p_i$ and $p_j$ come from an internal parent momentum

$$
P_{ij}=p_i+p_j.
$$

The parent propagator contains

$$
\frac{i}{P_{ij}^2+i\epsilon}
=
\frac{i}{s_{ij}+i\epsilon}.
$$

As $p_i$ and $p_j$ become parallel,

$$
s_{ij}=2E_iE_j(1-\cos\theta_{ij})
\simeq
E_iE_j\theta_{ij}^2,
$$

so the propagator becomes singular. Equivalently, in transverse-momentum variables,

$$
\frac{1}{s_{ij}}
\simeq
\frac{z(1-z)}{\mathbf k_\perp^2}.
$$

The phase space supplies a matching logarithmic measure. Thus a typical collinear contribution has the form

$$
\frac{d\mathbf k_\perp^2}{\mathbf k_\perp^2},
$$

which logarithmically diverges at small $\mathbf k_\perp^2$.

## Factorization of squared amplitudes

For an unpolarized leading-power discussion, the squared amplitude in a final-state collinear limit has the schematic form

$$
|\mathcal M_{n+1}(\ldots,p_i,p_j,\ldots)|^2
\simeq
\frac{2g_s^2}{s_{ij}}
P_{a\to bc}(z)
|\mathcal M_n(\ldots,P_{ij},\ldots)|^2.
$$

The lower-multiplicity amplitude treats the two daughters as a single parent parton of momentum $P_{ij}$. The splitting function $P_{a\to bc}(z)$ contains the spin and color information that survives after averaging or summing over unresolved degrees of freedom.

At the amplitude level one writes more precisely

$$
\mathcal M_{n+1}
\longrightarrow
\operatorname{Split}_{a\to bc}(z,k_\perp)
\mathcal M_n,
$$

where $\operatorname{Split}_{a\to bc}$ can carry helicity and color indices. The squared splitting functions below are the form most useful for first-pass cross-section calculations.

## Leading splitting functions

With $z$ defined as the momentum fraction carried by the first named daughter, the unregularized leading QCD splitting functions are

| Splitting | Kernel |
|---|---|
| $q\to qg$ | $P_{q\to qg}(z)=C_F\dfrac{1+z^2}{1-z}$ |
| $q\to gq$ | $P_{q\to gq}(z)=C_F\dfrac{1+(1-z)^2}{z}$ |
| $g\to gg$ | $P_{g\to gg}(z)=2C_A\left[\dfrac{z}{1-z}+\dfrac{1-z}{z}+z(1-z)\right]$ |
| $g\to q\bar q$ | $P_{g\to q\bar q}(z)=T_R\left[z^2+(1-z)^2\right]$ |

For QED, the fermion-to-fermion-photon kernel is the Abelian version of $q\to qg$:

$$
P_{f\to f\gamma}(z)
=Q_f^2\frac{1+z^2}{1-z},
$$

where $z$ is the fraction carried by the final fermion.

These are **unregularized** kernels. The endpoint singularities at $z=0$ or $z=1$ overlap with soft physics. In DGLAP evolution and fully inclusive cross sections, virtual corrections and momentum conservation convert these expressions into plus distributions and delta-function terms. Those refinements belong to the factorization and DGLAP pages; here the key point is the universal collinear structure.

## The small-angle picture

For two massless particles with energies $E_i$ and $E_j$ and small opening angle $\theta_{ij}$,

$$
p_i\cdot p_j
=E_iE_j(1-\cos\theta_{ij})
\simeq
\frac{E_iE_j\theta_{ij}^2}{2}.
$$

Therefore

$$
s_{ij}=2p_i\cdot p_j
\simeq
E_iE_j\theta_{ij}^2.
$$

A collinear integral may therefore appear as

$$
\int\frac{d\theta^2}{\theta^2}.
$$

This is the geometric content of a jet: many particles with small relative angles behave, for sufficiently inclusive measurements, like a single energetic object carrying the total momentum.

## Mass as a collinear regulator

Massless particles produce true collinear singularities in perturbation theory. A nonzero mass cuts off the singularity. If an energetic particle of mass $m$ participates in a hard process with scale $Q$, a typical collinear logarithm becomes

$$
\int_{m^2}^{Q^2}\frac{d\mathbf k_\perp^2}{\mathbf k_\perp^2}
=
\log\frac{Q^2}{m^2}.
$$

Thus a finite electron mass regulates QED collinear divergences, but at high energies it leaves large logarithms such as

$$
\alpha\log\frac{Q^2}{m_e^2}.
$$

These logarithms are physical reminders that radiation nearly parallel to a light charged particle is hard to resolve. In QCD, light quark masses are often negligible compared to collider scales, so collinear factorization is the natural language.

## Final-state collinear safety

A final-state observable is collinear safe if replacing two collinear particles by their combined parent does not change the measured value at leading power:

$$
V_{n+1}(\ldots,p_i,p_j,\ldots)
\longrightarrow
V_n(\ldots,p_i+p_j,\ldots)
\qquad
(p_i\parallel p_j).
$$

For such observables, unresolved collinear splittings are summed inclusively. The real collinear singularity cancels against the corresponding virtual singularity.

Examples of collinear-safe or collinear-organized quantities include:

| Observable type | Collinear behavior |
|---|---|
| total inclusive decay rate into hadrons | final-state collinear singularities cancel |
| jet cross section with an infrared-safe jet algorithm | collinear particles are clustered into the same jet |
| event shapes such as thrust | collinear splittings preserve the leading event shape |
| identified bare parton | not physical and not collinear safe |
| identified hadron spectrum | requires fragmentation functions |
| photon isolation with overly strict vetoes | may spoil infrared safety unless defined carefully |

The slogan is useful: detectors see jets, not isolated massless colored partons.

## Initial-state collinear singularities

Initial-state collinear divergences are different. In a hadron collision, the initial proton is fixed. We do not sum inclusively over a proton plus an unresolved collinear gluon in the same way that we sum over unobserved final-state fragments. Instead, collinear radiation associated with the incoming hadron is absorbed into parton distribution functions.

A schematic factorized cross section is

$$
\sigma_{AB\to X}
=
\sum_{i,j}
\int_0^1 dx_1\,dx_2\,
 f_{i/A}(x_1,\mu)
 f_{j/B}(x_2,\mu)
 \hat\sigma_{ij\to X}(x_1,x_2,Q,\mu).
$$

The finite, scale-dependent functions $f_{b/h}(\xi,\mu)$ are nonperturbative inputs. Their dependence on the factorization scale $\mu$ is perturbatively controlled by DGLAP equations,

$$
\mu\frac{d}{d\mu}f_{a/h}(x,\mu)
=
\sum_b\int_x^1\frac{dz}{z}
\frac{\alpha_s(\mu)}{\pi}
P_{a\leftarrow b}(z)
 f_{b/h}\left(\frac{x}{z},\mu\right)+\cdots,
$$

with convention-dependent factors of $2$ depending on whether one differentiates with respect to $\mu$ or $\mu^2$. The important point is not the normalization in this preview formula. It is that the same universal collinear splitting kernels that appear in amplitudes also govern the scale dependence of PDFs.

## Soft-collinear overlap

Soft and collinear limits overlap. For example, in

$$
P_{q\to qg}(z)=C_F\frac{1+z^2}{1-z},
$$

where $z$ is the final quark momentum fraction, the endpoint

$$
z\to1
$$

means that the gluon carries momentum fraction $1-z\to0$. The gluon is both soft and collinear. This region can produce double logarithms,

$$
\alpha_s\log^2\frac{Q^2}{m^2},
$$

or double infrared poles in dimensional regularization.

A careful calculation must avoid double-counting the soft-collinear overlap. Different formalisms do this with different names: subtraction terms, plus distributions, zero-bin subtractions, soft functions, jet functions, beam functions, or rapidity regulators. The common physics is the same: soft and collinear approximations describe overlapping regions of momentum space and must be combined consistently.

## What makes an observable collinear safe

A final-state observable is **collinear safe** if the measurement function obeys

$$
F_{n+1}(p_1,\ldots,p_b,p_c,\ldots)
\xrightarrow{p_b\parallel p_c}
F_n(p_1,\ldots,p_b+p_c,\ldots).
$$

In words: two exactly collinear particles are measured as one combined object.

This criterion is why jet algorithms matter. A collinear-safe jet algorithm clusters collinear fragments into the same jet. An event shape such as thrust is collinear safe because replacing a particle by two exactly parallel particles leaves the leading thrust axis and total momentum flow unchanged. An observable that counts the exact number of partons is not collinear safe.

For initial-state hadrons, exact cancellation is not the right language. The incoming proton is a nonperturbative bound state, so collinear radiation along the beam is absorbed into PDFs. For identified final-state hadrons, the analogous long-distance sensitivity is absorbed into fragmentation functions.

## Masses as physical regulators

A nonzero mass removes the exact collinear degeneracy. The angular denominator is effectively shifted from

$$
\theta^2
$$

to a form of order

$$
\theta^2+\frac{m^2}{E^2}.
$$

Thus

$$
\int_0^{R^2}\frac{d\theta^2}{\theta^2+m^2/E^2}
=
\log\left(1+\frac{E^2R^2}{m^2}\right).
$$

For $E R\gg m$, this is approximately

$$
\log\frac{E^2R^2}{m^2}.
$$

The mass makes the answer finite, but it can leave a large logarithm. This is why small fermion masses cannot always be ignored even when they are negligible in the hard matrix element.

## Common pitfalls

**Calling all infrared divergences soft.** Collinear divergences can occur at finite energy. The singular variable is angle or transverse momentum, not energy.

**Treating a fixed number of partons as an observable.** Partons are calculation variables. Infrared-safe observables are defined in terms of inclusive hadronic energy flow, jets, or sufficiently inclusive identified objects.

**Forgetting the endpoints of splitting functions.** Singularities in $z\to0$ or $z\to1$ are usually soft-collinear regions, not pure collinear regions at fixed energy fraction.

**Using real-emission kernels as full evolution kernels.** DGLAP kernels include plus distributions and delta-function terms generated by virtual corrections and conservation laws.

**Expecting initial-state collinear singularities to cancel like final-state ones.** In hadron scattering, initial-state collinear singularities are absorbed into PDFs because the incoming hadron is a long-distance object.

**Confusing a regulator with a factorization scale.** A regulator is removed. A factorization scale remains as an arbitrary separation scale whose dependence cancels between short- and long-distance factors up to perturbative truncation.

## Relations to other pages

- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) explains the low-energy infrared limit and its overlap with collinear radiation.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) gives the observable-level criterion behind infrared safety.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) fixes the hard-scattering normalization before unresolved radiation is included.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains why collinear logarithms can appear as infrared poles.
- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) and [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) provide the first hard amplitudes from which collinear limits can be taken.
- [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) and [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) develop the all-order organization of soft and collinear sectors.

## Research status

- **Established:** Leading collinear factorization, splitting amplitudes, leading-order splitting functions, final-state collinear safety, and PDF factorization are standard parts of perturbative gauge theory.
- **Active:** Higher-loop splitting functions, transverse-momentum-dependent factorization, endpoint resummation, jet substructure, heavy-quark mass effects, Glauber exchange, and power corrections remain major precision-frontier topics.
- **Convention-dependent:** The definition of $z$, the normalization of splitting functions, the color-generator convention, and the factorization scheme vary across sources. The existence of a universal collinear singular factor is not convention-dependent.

## Exercises

### Exercise 1: Small-angle invariant mass

For two massless final-state particles with energies $E_b$ and $E_c$ and angle $\theta$ between them, show that

$$
s_{bc}=2p_b\cdot p_c\simeq E_bE_c\theta^2
$$

for small $\theta$.

<details>
<summary><strong>Solution</strong></summary>

For massless momenta,

$$
p_b\cdot p_c=E_bE_c(1-\cos\theta).
$$

Thus

$$
s_{bc}=2p_b\cdot p_c=2E_bE_c(1-\cos\theta).
$$

For small angle,

$$
1-\cos\theta\simeq\frac{\theta^2}{2},
$$

so

$$
s_{bc}\simeq E_bE_c\theta^2.
$$

</details>

### Exercise 2: The angular logarithm

Suppose the collinear emission probability contains

$$
dP=A\frac{d\theta^2}{\theta^2}
$$

between angular cutoffs $\theta_{\min}$ and $\theta_{\max}$. Compute the integral.

<details>
<summary><strong>Solution</strong></summary>

Integrating gives

$$
P=A\int_{\theta_{\min}^2}^{\theta_{\max}^2}\frac{d\theta^2}{\theta^2}.
$$

Therefore

$$
P=A\log\frac{\theta_{\max}^2}{\theta_{\min}^2}
=2A\log\frac{\theta_{\max}}{\theta_{\min}}.
$$

The divergence appears as $\theta_{\min}\to0$.

</details>

### Exercise 3: Pair invariant mass from transverse momentum

Using the leading-power collinear relation

$$
s_{bc}\simeq\frac{\mathbf k_\perp^2}{z(1-z)},
$$

explain why $s_{bc}\to0$ at fixed $z$ is equivalent to $\mathbf k_\perp^2\to0$.

<details>
<summary><strong>Solution</strong></summary>

For fixed $0<z<1$, the denominator $z(1-z)$ is finite and positive. Thus the only way for

$$
s_{bc}=\frac{\mathbf k_\perp^2}{z(1-z)}
$$

to approach zero is for

$$
\mathbf k_\perp^2\to0.
$$

This is why the transverse-momentum integral $d\mathbf k_\perp^2/\mathbf k_\perp^2$ captures the collinear singularity.

</details>

### Exercise 4: Soft endpoint of the quark splitting kernel

For

$$
P_{q\to qg}(z)=C_F\frac{1+z^2}{1-z},
$$

where $z$ is the quark momentum fraction, identify the soft-gluon endpoint and find the leading singular behavior.

<details>
<summary><strong>Solution</strong></summary>

The gluon momentum fraction is $1-z$. The gluon becomes soft when

$$
1-z\to0,
\qquad z\to1.
$$

Near $z=1$,

$$
1+z^2\to2,
$$

so

$$
P_{q\to qg}(z)\sim\frac{2C_F}{1-z}.
$$

This endpoint singularity is the soft-collinear overlap.

</details>

### Exercise 5: Mass-regulated angular integral

Compute

$$
I=\int_0^{R^2}\frac{d\theta^2}{\theta^2+m^2/E^2}.
$$

What is the result when $ER\gg m$?

<details>
<summary><strong>Solution</strong></summary>

The integral is

$$
I=
\left[
\log\left(\theta^2+\frac{m^2}{E^2}\right)
\right]_0^{R^2}.
$$

Therefore

$$
I=
\log\left(R^2+\frac{m^2}{E^2}\right)
-
\log\left(\frac{m^2}{E^2}\right)
=
\log\left(1+\frac{E^2R^2}{m^2}\right).
$$

If $ER\gg m$, then

$$
I\simeq\log\frac{E^2R^2}{m^2}.
$$

The mass regulates the collinear divergence but leaves a large logarithm.

</details>

### Exercise 6: A non-collinear-safe parton count

Consider an observable that counts the number of final-state massless partons above a fixed energy threshold. Is this observable collinear safe? Explain using a single hard parton that splits into two exactly collinear daughters.

<details>
<summary><strong>Solution</strong></summary>

The observable is not collinear safe. Before the splitting, the event contains one hard parton above threshold. After the splitting, the two daughters are exactly collinear and have total momentum equal to the original parent momentum. If both daughters are above threshold, the observable counts two partons instead of one.

Thus the measurement function does not obey

$$
F_{n+1}(\ldots,p_i,p_j,\ldots)
\to
F_n(\ldots,p_i+p_j,\ldots)
\qquad
(p_i\parallel p_j).
$$

Because the observable changes under an unresolved collinear splitting, the real collinear singularity cannot cancel against the virtual singularity in a massless calculation. A jet observable avoids this by clustering exactly collinear particles into one jet.

</details>

## References

- T. Kinoshita, “Mass Singularities of Feynman Amplitudes,” *Journal of Mathematical Physics* **3** (1962), and T. D. Lee and M. Nauenberg, “Degenerate Systems and Mass Singularities,” *Physical Review* **133** (1964), for the general cancellation logic of mass and infrared singularities.
- G. Altarelli and G. Parisi, “Asymptotic Freedom in Parton Language,” *Nuclear Physics B* **126** (1977), for the classic splitting-function evolution equations.
- V. N. Gribov and L. N. Lipatov, and Y. L. Dokshitzer, for the other foundational pieces of DGLAP evolution.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for infrared effects and mass singularities in scattering.
- M. Srednicki, *Quantum Field Theory*, §26, for an introductory discussion of infrared divergences.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 32, and 36, for infrared divergences, jets, factorization, and SCET motivation.
- G. Sterman, *An Introduction to Quantum Field Theory*, and J. C. Collins, *Foundations of Perturbative QCD*, for systematic treatments of collinear factorization and PDFs.

## Version history

- **2026-06-13:** Initial polished draft. Establishes collinear kinematics, angular logarithms, splitting functions, final-state collinear safety, initial-state PDF factorization, soft-collinear overlap, and solved exercises.
