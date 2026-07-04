---
title: "Bloch–Nordsieck Theorem"
description: "The soft-photon cancellation theorem behind infrared-finite inclusive QED rates, soft exponentiation, and the failure of exact fixed-photon-number scattering."
sidebar:
  label: "Bloch–Nordsieck Theorem"
  order: 3
level: Graduate
status: "Polished draft"
source: "Bloch–Nordsieck; Yennie–Frautschi–Suura; Weinberg Vol. I on infrared effects; Srednicki §26; Schwartz ch. 20"
topics:
  - infrared divergences
  - soft photons
  - inclusive observables
  - real–virtual cancellation
  - exponentiation
canonicalTopics:
  - bloch-nordsieck-theorem
  - soft-photon-cancellation
  - inclusive-qed-rates
  - infrared-exponentiation
researchStatus:
  established:
    - "The cancellation of soft-photon infrared divergences in sufficiently inclusive QED probabilities is a standard consequence of soft factorization and unitarity."
  active:
    - "Modern work refines the same ideas for non-Abelian gauge theories, subleading soft structure, coherent-state asymptotic dynamics, detector-sensitive observables, and precision resummation."
---

## Summary

The **Bloch–Nordsieck theorem** explains why soft-photon infrared divergences do not spoil measurable QED rates. The theorem says, in its standard perturbative form, that if charged particles are massive and one sums over all photons too soft to be experimentally resolved, the dependence on the infrared regulator cancels between real soft emission and virtual soft loops.

For a hard process involving external charged particles, the leading soft-photon theorem gives

$$
\mathcal M_{n+1}(p_1,\ldots,p_n;k,\varepsilon)
\simeq
\left[
e\sum_i \eta_i Q_i
\frac{p_i\cdot \varepsilon^*(k)}{p_i\cdot k}
\right]
\mathcal M_n(p_1,\ldots,p_n),
$$

where $k$ is the soft photon momentum, $Q_i$ is the charge in units of $e$, and $\eta_i=+1$ for outgoing charged legs and $\eta_i=-1$ for incoming charged legs. The factor $1/(p_i\cdot k)$ makes both real soft emission and virtual soft exchange logarithmically singular.

The cancellation has a simple schematic form. With an infrared regulator $\lambda$, such as a small photon mass or dimensional regularization parameter, one finds

$$
d\sigma_{\rm virtual}
=
d\sigma_{\rm hard}
\left[1+A\log \lambda+\text{finite}\right],
$$

while unresolved real emission below detector resolution $\Delta E$ gives

$$
d\sigma_{\rm real}(\omega<\Delta E)
=
d\sigma_{\rm hard}
\left[-A\log \lambda+\text{finite}(\Delta E)\right].
$$

The unphysical $\log\lambda$ cancels in the inclusive rate. The physical answer still depends on the resolution $\Delta E$. That dependence is not a bug: different detectors and different event definitions really do ask different questions.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Bloch–Nordsieck cancellation between virtual soft loops and real unresolved photons](/figures/perturbative-qft/bloch-nordsieck-theorem.svg)

<figcaption>

The virtual soft region and the real unresolved-emission region contain equal and opposite dependence on the infrared regulator $\lambda$. The inclusive rate is finite as $\lambda\to0$, but it retains physical dependence on the detector resolution $\Delta E$.

</figcaption>
</figure>

## Prerequisites

You should know [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/), and the [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/). For conventions, use [Conventions and Notation](/perturbative-qft/conventions/) and the qft.org mostly-minus metric.

## Core idea

The theorem is often stated as a cancellation theorem, but its deeper message is about what counts as a physical scattering question.

In a theory with a massless photon, arbitrarily low-energy photons cost arbitrarily little energy. A detector with finite resolution cannot distinguish

$$
f
$$

from

$$
f+\gamma_{\rm soft},
\qquad
f+2\gamma_{\rm soft},
\qquad
f+3\gamma_{\rm soft},
\qquad\ldots
$$

provided the total unresolved photon energy is below the detector threshold. Asking for exactly zero emitted photons is therefore not an idealized version of the physical measurement. It is a different, unphysical question.

The exclusive fixed-photon-number rate is infrared singular order by order and, after soft exponentiation, the probability of emitting exactly no photons above zero energy goes to zero as the infrared regulator is removed. The measurable object is instead an inclusive rate,

$$
d\sigma_{\rm incl}(\Delta E)
=
\sum_{n=0}^{\infty}
 d\sigma\bigl(\text{hard final state}+n\text{ photons with total unresolved energy}<\Delta E\bigr).
$$

The Bloch–Nordsieck theorem says that this inclusive object is free of soft-photon infrared regulator dependence.

:::note[The slogan]
A charged-particle scattering process in QED is not “the hard process and no photons.” It is “the hard process plus whatever soft radiation the measurement cannot resolve.”
:::

## Setup and conventions

Consider a hard QED process with charged external particles,

$$
i\to f,
$$

with hard amplitude $\mathcal M_{fi}$. We regulate the infrared by a parameter $\lambda$. One may imagine a small photon mass, although dimensional regularization is usually cleaner in modern calculations. The regulator is only a device; the final inclusive answer must not depend on it.

Let $\Delta E$ denote the maximum total energy of unobserved photons. This energy cutoff is frame-dependent, so a fully realistic observable should be defined more carefully. For a first pass, take $\Delta E$ in the hard center-of-mass frame. The important hierarchy is

$$
\lambda \ll \Delta E \ll Q,
$$

where $Q$ is a hard scale in the process.

The theorem is cleanest in QED with massive charged particles. The masses prevent collinear divergences. The only infrared singularity is soft. If the charged particles are treated as massless, then collinear singularities appear and Bloch–Nordsieck by itself is not enough; the more general cancellation statement is the [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/), supplemented in collider settings by factorization.

## The theorem

A useful perturbative statement is:

:::note[Bloch–Nordsieck theorem]
In QED with massive charged external particles, inclusive probabilities summed over arbitrary numbers of unresolved soft photons are finite as the photon infrared regulator is removed, order by order in perturbation theory after ultraviolet renormalization.
:::

The word **inclusive** is doing serious work. The theorem does not say that every S-matrix element between Fock states is finite. It says that the physically relevant sum over degenerate soft-photon final states cancels the infrared divergence.

There is also an all-orders refinement: the soft singularities exponentiate. This exponentiation implies that fixed finite-photon-number exclusive probabilities are not the right asymptotic observables. With a nonzero chance to emit a photon in each logarithmic energy interval $d\omega/\omega$, the number of photons below any finite resolution is not fixed.

## Real soft emission

The leading soft-emission amplitude is universal:

$$
\mathcal M_{fi+\gamma}(k,\varepsilon)
\simeq
S(k,\varepsilon)\mathcal M_{fi},
$$

where

$$
S(k,\varepsilon)
=
e\sum_i \eta_i Q_i
\frac{p_i\cdot \varepsilon^*(k)}{p_i\cdot k}.
$$

Squaring and integrating over an unresolved photon gives

$$
d\sigma_{\rm real}^{\rm soft}
=
d\sigma_{\rm hard}
\int_{\omega<\Delta E}
\frac{d^3\mathbf k}{(2\pi)^3 2\omega}
\sum_{\rm pol}|S(k,\varepsilon)|^2.
$$

For a soft massless photon,

$$
\frac{d^3\mathbf k}{2\omega}
=
\frac{\omega\,d\omega\,d\Omega}{2}.
$$

The eikonal factor scales as

$$
|S(k,\varepsilon)|^2\sim \frac{1}{\omega^2},
$$

so the energy integral contains

$$
\int^{\Delta E}_{\lambda}\frac{d\omega}{\omega}
=
\log\frac{\Delta E}{\lambda}.
$$

This is the real-emission infrared divergence. It is positive, as an emission probability should be, and it grows as the regulator is removed.

The angular integral contains information about the charged external momenta. For massive external particles, it is finite. For massless external charged particles, it may develop collinear singularities when $k$ becomes parallel to an external momentum. That is exactly the limitation of the pure Bloch–Nordsieck statement.

## Virtual soft photons

Virtual soft photons appear when a photon of loop momentum $k$ is exchanged between external charged lines, or when a soft photon loop corrects an external charged line. In the soft region, the same eikonal denominators appear:

$$
\frac{1}{p_i\cdot k},
\qquad
\frac{1}{p_j\cdot k}.
$$

The virtual soft contribution has the same logarithmic sensitivity to $\lambda$ as real emission, but with the opposite sign in the inclusive probability. Schematically,

$$
d\sigma_{\rm virtual}^{\rm soft}
=
d\sigma_{\rm hard}
\left[-C\log\frac{Q}{\lambda}+\text{finite}\right],
$$

while real unresolved emission gives

$$
d\sigma_{\rm real}^{\rm soft}
=
d\sigma_{\rm hard}
\left[+C\log\frac{\Delta E}{\lambda}+\text{finite}\right]
$$

with matching regulator dependence. The sum is

$$
d\sigma_{\rm virtual}^{\rm soft}
+
d\sigma_{\rm real}^{\rm soft}
=
d\sigma_{\rm hard}
\left[-C\log\frac{Q}{\Delta E}+\text{finite}\right],
$$

where $\lambda$ has disappeared.

The remaining logarithm $\log(Q/\Delta E)$ is physical. If the detector is made more exclusive by lowering $\Delta E$, the rate changes. In the limit $\Delta E\to0$, one returns to the impossible question of zero unresolved radiation.

## Exponentiation

The theorem is not merely a one-loop accident. Multiple soft photons factorize. At leading soft order, emission of $n$ unresolved photons gives a product of $n$ soft factors and a Bose symmetry factor $1/n!$:

$$
d\sigma_{n\,\rm soft}
\simeq
 d\sigma_{\rm hard}
\frac{1}{n!}
\left[\int_{\omega<\Delta E}dP_{\rm soft}(k)\right]^n,
$$

where $dP_{\rm soft}$ denotes the one-photon soft emission probability measure.

Summing over $n$ produces an exponential. Virtual soft corrections exponentiate as well, with the sign needed by unitarity. The inclusive rate has the schematic form

$$
d\sigma_{\rm incl}(\Delta E)
=
d\sigma_{\rm hard}^{\rm finite}
\exp\left[-C\log\frac{Q}{\Delta E}+\cdots\right],
$$

or

$$
d\sigma_{\rm incl}(\Delta E)
\sim
 d\sigma_{\rm hard}^{\rm finite}
\left(\frac{\Delta E}{Q}\right)^C
$$

at leading logarithmic accuracy, with $C>0$ in ordinary charged scattering. The dots denote finite terms and subleading logarithms whose precise form depends on the process and observable.

This formula encodes the infrared catastrophe in a useful way. The probability of no radiation above an arbitrarily small energy threshold tends to zero, but the inclusive probability at finite resolution is well-defined.

## Physical interpretation

The soft-photon problem is not only a technical divergence. It reflects the long-range nature of electromagnetism.

A charged particle carries an electromagnetic field extending to infinity. When charged particles scatter, their velocities change, and the long-range field must adjust. That adjustment cannot be described by a finite number of ordinary Fock-space photons. The perturbative manifestation is the infinite population of arbitrarily soft photons.

There are two complementary ways to deal with this fact.

First, one can compute ordinary Fock-space amplitudes with an infrared regulator and form inclusive rates. This is the Bloch–Nordsieck route used in most practical perturbative calculations.

Second, one can try to define better asymptotic charged states dressed by coherent soft-photon clouds. This direction leads toward dressed-state approaches such as Faddeev–Kulish asymptotic states. Those approaches are conceptually important, but inclusive rates remain the most direct bridge to ordinary experiments.

## What the theorem does and does not say

The Bloch–Nordsieck theorem removes soft infrared regulator dependence from sufficiently inclusive QED probabilities. It does **not** say that every quantity is finite.

| Question | Bloch–Nordsieck answer |
|---|---|
| Exclusive amplitude with no photons | Infrared divergent order by order and not directly physical. |
| Inclusive rate with photons below $\Delta E$ summed | Infrared finite as $\lambda\to0$. |
| Dependence on detector resolution $\Delta E$ | Physical and generally logarithmic. |
| Collinear divergences for massless charged particles | Not handled by Bloch–Nordsieck alone. |
| Non-Abelian soft gluons | Similar soft ideas exist, but color, confinement, and factorization make the story richer. |
| Large logarithms $\log(Q/\Delta E)$ | Finite but may require resummation for precision. |

A finite observable can still be badly behaved in fixed-order perturbation theory if it contains large logarithms. Cancellation of the regulator is not the same as numerical convergence.

## Relation to unitarity

The cancellation has a unitarity flavor. Virtual soft corrections reduce the probability for the exclusive hard process, while real soft emissions move probability into experimentally indistinguishable final states. The inclusive sum restores the probability that the hard event occurred within the detector resolution.

At a schematic level,

$$
\text{probability lost from virtual soft loops}
+
\text{probability gained by unresolved real photons}
=
\text{finite}.
$$

This is the same basic logic that reappears in the optical theorem, Cutkosky rules, and the KLN theorem. The details differ, but the moral is stable: probabilities, not individual diagrams, are the physical objects.

## Common pitfalls

**Thinking soft photons are optional decorations.** They are not optional in a theory with massless photons. They are part of the physically measured event.

**Expecting the exclusive no-photon rate to be finite.** Exact fixed-photon-number probabilities are not robust observables in QED. The all-orders probability of exactly no photons above zero energy vanishes in ordinary charged scattering.

**Confusing regulator cancellation with detector independence.** The unphysical regulator $\lambda$ cancels. The physical resolution $\Delta E$ remains.

**Using Bloch–Nordsieck for massless collinear problems.** Massive charged particles regulate collinear singularities. If charged particles are massless, one needs the KLN theorem and often factorization.

**Treating QCD as QED with color labels.** Soft gluon emission factorizes, but non-Abelian color charge changes under emission and observable hadrons are color singlets. QCD infrared physics requires the broader language of factorization, jets, PDFs, and confinement.

## Relations to other pages

- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) derives the eikonal factor and the logarithmic soft integral.
- [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) explains the singularities not removed by the soft-only Bloch–Nordsieck statement.
- [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) gives the more general cancellation theorem for sums over degenerate initial and final states.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) explains why physically measured rates are sums over unresolved final states.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) and [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/) connect cancellation to unitarity.
- Later factorization pages will explain how the same cancellation logic is organized for QCD observables.

## Research status

- **Established:** Soft-photon factorization, real–virtual cancellation in inclusive QED rates, and soft exponentiation are textbook-standard.
- **Active:** Precise soft resummation, subleading soft theorems, coherent asymptotic states, infrared structure in gravity, non-Abelian soft radiation, and detector-level definitions of infrared-safe observables remain active topics.
- **Speculative:** The basic theorem is not speculative, but its relation to asymptotic symmetries, memory effects, celestial amplitudes, and dressed-state formulations continues to be a lively conceptual frontier.

## Exercises

### Exercise 1: The logarithm from soft phase space

Use

$$
d\Pi_k=\frac{d^3\mathbf k}{(2\pi)^3 2\omega}
$$

and $|S(k)|^2\sim 1/\omega^2$ to show that the real-emission soft integral contains $\int d\omega/\omega$.

<details>
<summary><strong>Solution</strong></summary>

For a massless photon, $\omega=|\mathbf k|$ and

$$
d^3\mathbf k=\omega^2 d\omega\,d\Omega.
$$

Therefore

$$
d\Pi_k
=
\frac{\omega^2d\omega\,d\Omega}{(2\pi)^3 2\omega}
=
\frac{\omega\,d\omega\,d\Omega}{2(2\pi)^3}.
$$

Multiplying by $|S(k)|^2\sim1/\omega^2$ gives

$$
d\Pi_k |S(k)|^2
\sim
\frac{d\omega}{\omega}\,d\Omega.
$$

Thus the energy integral is logarithmic in the soft region.

</details>

### Exercise 2: Regulator cancellation in a toy model

Suppose the virtual correction and unresolved real-emission correction are

$$
d\sigma_{\rm virt}
=d\sigma_0\left[1-C\log\frac{Q}{\lambda}\right],
$$

and

$$
d\sigma_{\rm real}
=d\sigma_0 C\log\frac{\Delta E}{\lambda}.
$$

Add them and show that $\lambda$ cancels at order $C$.

<details>
<summary><strong>Solution</strong></summary>

The inclusive rate at this order is

$$
\begin{aligned}
d\sigma_{\rm incl}
&=d\sigma_{\rm virt}+d\sigma_{\rm real}\\
&=d\sigma_0\left[1-C\log\frac{Q}{\lambda}
+C\log\frac{\Delta E}{\lambda}\right].
\end{aligned}
$$

Use

$$
\log\frac{Q}{\lambda}-\log\frac{\Delta E}{\lambda}
=
\log\frac{Q}{\Delta E}.
$$

Then

$$
d\sigma_{\rm incl}
=d\sigma_0\left[1-C\log\frac{Q}{\Delta E}\right].
$$

The regulator $\lambda$ is gone. The detector resolution $\Delta E$ remains.

</details>

### Exercise 3: Why the exact no-photon probability vanishes

Assume unresolved soft emissions are Poisson distributed with mean

$$
\bar N=C\int_{\lambda}^{Q}\frac{d\omega}{\omega}
=C\log\frac{Q}{\lambda},
$$

where $C>0$. What happens to the probability $P_0=e^{-\bar N}$ of emitting zero photons as $\lambda\to0$?

<details>
<summary><strong>Solution</strong></summary>

The zero-emission probability is

$$
P_0
=\exp\left[-C\log\frac{Q}{\lambda}\right]
=\left(\frac{\lambda}{Q}\right)^C.
$$

Since $C>0$,

$$
\lim_{\lambda\to0}P_0=0.
$$

So the exact no-photon final state has zero probability once arbitrarily soft photons are allowed. This is the all-orders version of the infrared problem.

</details>

### Exercise 4: Bloch–Nordsieck versus KLN

Why is Bloch–Nordsieck enough for QED with massive external electrons but not enough for massless charged external particles?

<details>
<summary><strong>Solution</strong></summary>

For massive external charged particles, the soft singularity occurs when $\omega\to0$. The particle mass prevents the emitted photon from becoming exactly collinear with a massless charged particle in a singular way. Thus the leading infrared issue is soft, and Bloch–Nordsieck cancellation applies.

For massless charged particles, the denominator

$$
p\cdot k=E\omega(1-\cos\theta)
$$

can vanish not only when $\omega\to0$ but also when $\theta\to0$. This is a collinear singularity. Bloch–Nordsieck cancels soft singularities, but the full massless problem requires the more general KLN theorem and, in many physical settings, factorization into long-distance functions.

</details>

## References

- F. Bloch and A. Nordsieck, “Note on the Radiation Field of the Electron,” *Physical Review* **52** (1937), 54–59.
- D. R. Yennie, S. C. Frautschi, and H. Suura, “The Infrared Divergence Phenomena and High-Energy Processes,” *Annals of Physics* **13** (1961), 379–452.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for infrared effects, soft photons, and the relation between inclusive rates and finite observables.
- M. Srednicki, *Quantum Field Theory*, especially §26, for infrared divergences in perturbative scattering.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 20, for infrared divergences, real–virtual cancellation, and collider-oriented examples.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for the conceptual relation between scattering, soft radiation, and physical inclusive probabilities.

## Version history

- **2026-06-13:** Initial polished draft for the Perturbative QFT and Scattering volume. Includes the soft-factor statement, real–virtual cancellation, exponentiation, caveats, and solved exercises.
