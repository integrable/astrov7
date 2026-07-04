---
title: "Soft Photon Theorem"
description: "Weinberg's leading soft photon theorem, Low's subleading structure, and the Ward-identity logic behind universal photon emission."
sidebar:
  label: "Soft Photon Theorem"
  order: 6
level: Graduate
status: "Polished draft"
source: "Low 1958; Burnett–Kroll; Weinberg 1965; Weinberg Vol. I; Srednicki section 26; Schwartz ch. 20"
topics:
  - soft photon theorem
  - infrared divergences
  - Ward identities
  - eikonal approximation
  - asymptotic symmetries
canonicalTopics:
  - soft-photon-theorem
  - leading-soft-photon-factor
  - low-theorem
  - soft-ward-identity
researchStatus:
  established:
    - "The leading soft photon theorem is a universal consequence of gauge invariance and the pole structure of external charged particles; Low's theorem fixes the subleading soft behavior under standard analyticity assumptions."
  active:
    - "Loop-level refinements, massless charged particles, dressed asymptotic states, asymptotic symmetries, celestial formulations, and subleading soft structures remain active research topics."
---

## Summary

The **soft photon theorem** states that an amplitude with an extra photon of momentum $k$ factorizes in the limit $k^0\to0$. To leading order, the photon couples only to the charges and momenta of the external hard particles:

$$
\mathcal M_{n+1}(p_1,\ldots,p_n;k,\varepsilon)
=
\left[
 e\sum_{i=1}^n\eta_i Q_i
 \frac{p_i\cdot\varepsilon^*(k)}{p_i\cdot k}
\right]
\mathcal M_n(p_1,\ldots,p_n)
+
O(k^0).
$$

Here $Q_i$ is the charge of external leg $i$ in units of $e$, and $\eta_i=+1$ for outgoing charged particles and $\eta_i=-1$ for incoming charged particles. This is the same leading factor derived from the [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/).

A more refined version expands the amplitude as

$$
\mathcal M_{n+1}
=
\left(S_\gamma^{\rm lead}+S_\gamma^{\rm sub}+O(k)\right)
\mathcal M_n,
$$

with

$$
S_\gamma^{\rm lead}
=
e\sum_i\eta_i Q_i
\frac{p_i\cdot\varepsilon^*}{p_i\cdot k},
\qquad
S_\gamma^{\rm sub}
=
-i e\sum_i\eta_i Q_i
\frac{\varepsilon_\mu^*k_\nu J_i^{\mu\nu}}{p_i\cdot k}.
$$

The angular momentum operator $J_i^{\mu\nu}$ acts on the momentum and spin labels of hard leg $i$. For elementary minimally coupled particles this is the standard form of Low's subleading soft theorem. For composite particles, the subleading term also knows about static electromagnetic moments.

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![The soft photon theorem expands an amplitude with one low-energy photon into universal leading and subleading soft factors multiplying the hard amplitude](/figures/perturbative-qft/soft-photon-theorem.svg)

<figcaption>

The leading soft photon sees only external charges and momenta. The subleading soft photon also sees total angular momentum. Gauge invariance of the leading term reduces to charge conservation, while the finite terms beyond Low's theorem contain process-dependent structure.

</figcaption>
</figure>

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/), [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/), and [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/).

## Core idea

A photon with very low energy has very long wavelength. It cannot resolve the details of the hard scattering. At leading order, it only measures the total electromagnetic charge flow carried by external particles.

That is why the amplitude with an extra soft photon takes the form

$$
\mathcal M_{n+1}^{\rm soft}
=
\text{soft factor}\times \mathcal M_n.
$$

The soft theorem is stronger than a mnemonic for infrared divergences. It is an amplitude-level statement about the first terms in an expansion in the soft momentum $k$. The leading term is fixed by external-line poles. The subleading term is fixed, under standard assumptions, by gauge invariance and angular momentum acting on the hard amplitude. Terms beyond this order contain genuinely process-dependent information.

The theorem explains several otherwise mysterious facts at once:

| Fact | Soft-theorem explanation |
|---|---|
| Real soft radiation has a universal singularity | the leading factor is $1/(p_i\cdot k)$ |
| Gauge invariance forces charge conservation | replace $\varepsilon$ by $k$ in the leading factor |
| Spin appears later than charge | spin enters through $J_i^{\mu\nu}$ at subleading order |
| Inclusive rates are finite | soft real emission cancels soft virtual exchange |

The slogan is:

$$
\text{a soft photon sees charges first, angular momenta second, and structure later.}
$$

## Setup and conventions

We use qft.org scattering conventions,

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi},
$$

mostly-minus metric, and the incoming/outgoing sign convention

$$
\eta_i=
\begin{cases}
+1, & \text{outgoing charged leg},\\
-1, & \text{incoming charged leg}.
\end{cases}
$$

The photon has momentum $k^\mu$ and polarization $\varepsilon^\mu(k)$, with

$$
k^2=0,
\qquad
k^0=\omega\to0,
\qquad
k\cdot\varepsilon(k)=0.
$$

The displayed formulas are for amplitudes with the overall momentum-conserving delta function stripped off. This matters for the subleading theorem, because the orbital angular momentum operator differentiates with respect to hard momenta. One should act on a set of independent momentum variables, or use a convention in which the momentum-conservation delta function has already been removed.

## Leading theorem

The leading soft photon theorem is

$$
\mathcal M_{n+1}(p_i;k,\varepsilon)
=
S_\gamma^{\rm lead}(k,\varepsilon)\mathcal M_n(p_i)
+
O(k^0),
$$

where

$$
S_\gamma^{\rm lead}(k,\varepsilon)
=
e\sum_{i=1}^n\eta_i Q_i
\frac{p_i\cdot\varepsilon^*(k)}{p_i\cdot k}.
$$

This expression is universal. It does not depend on the spin of the charged particle, the short-distance interaction inside the hard process, or the number of hard particles. It only depends on the external charged momenta.

A quick derivation comes from external-line emission. For a scalar external line,

$$
(p+k)^2-m^2=2p\cdot k
$$

near the mass shell. The scalar-photon vertex gives $(2p+k)^\mu\simeq2p^\mu$, so the ratio gives $p^\mu/(p\cdot k)$. For a spinor external line, the Dirac numerator reduces to the same factor by the on-shell Dirac equation. This is exactly the eikonal approximation.

Internal emissions are less singular. If the soft photon attaches inside a genuinely hard subdiagram, no internal hard propagator is forced close to its mass shell by $k\to0$. Such contributions are at most $O(k^0)$ and cannot change the leading $1/k$ theorem.

## Gauge invariance and the Ward identity

The leading theorem passes a decisive check. Gauge invariance says that the amplitude should vanish when the external photon polarization is replaced by its momentum:

$$
\varepsilon^\mu(k)\longrightarrow k^\mu.
$$

The leading soft factor becomes

$$
S_\gamma^{\rm lead}(k,k)
=
e\sum_i\eta_i Q_i\frac{p_i\cdot k}{p_i\cdot k}
=
e\sum_i\eta_i Q_i.
$$

Thus the leading soft theorem is compatible with the Ward identity exactly when

$$
\sum_i\eta_i Q_i=0.
$$

This is charge conservation between incoming and outgoing hard states.

This argument also explains why one should not interpret the soft factor as emission from one preferred external line. Individual external-line terms are not gauge invariant. Gauge invariance belongs to the sum over all charged external legs.

## Subleading theorem and Low's result

The next term in the soft expansion is often called **Low's theorem**. For elementary minimally coupled external particles, it can be written compactly as

$$
S_\gamma^{\rm sub}(k,\varepsilon)
=
-i e\sum_i\eta_i Q_i
\frac{\varepsilon_\mu^*(k)k_\nu J_i^{\mu\nu}}{p_i\cdot k}.
$$

Here

$$
J_i^{\mu\nu}=L_i^{\mu\nu}+\Sigma_i^{\mu\nu}
$$

is the total angular momentum operator acting on external leg $i$. The orbital part is

$$
L_i^{\mu\nu}
=
i\left(
 p_i^\mu\frac{\partial}{\partial p_{i\nu}}
-
 p_i^\nu\frac{\partial}{\partial p_{i\mu}}
\right),
$$

and $\Sigma_i^{\mu\nu}$ acts on spin or polarization labels. For a scalar external particle, $\Sigma_i^{\mu\nu}=0$.

The subleading theorem has a simple interpretation: after the soft photon sees the external charge moving along a straight line, the next correction sees how the hard amplitude changes under an infinitesimal Lorentz transformation of that external leg.

There are two caveats worth taking seriously.

First, the subleading term acts on the stripped hard amplitude. Applying $J_i^{\mu\nu}$ directly to an expression with an overall momentum-conserving delta function can produce misleading contact terms unless the convention is stated.

Second, for composite particles or non-minimal electromagnetic couplings, Low's theorem includes static electromagnetic data such as magnetic moments. Those are still low-energy data, but they are not determined solely by charge and momentum.

## What is universal and what is not

The soft expansion has a hierarchy:

$$
\mathcal M_{n+1}
=
\frac{1}{\omega}\mathcal M^{(-1)}
+
\mathcal M^{(0)}
+
\omega \mathcal M^{(1)}
+\cdots.
$$

For photon emission from massive charged particles:

| Order | Scaling | Status |
|---|---:|---|
| leading | $1/\omega$ | fixed by charge and external momenta |
| subleading | $\omega^0$ | fixed by Low's theorem, angular momentum, and possible static moments |
| sub-subleading and beyond | $\omega^1$ and higher | process-dependent structure |

The non-universal terms are not unimportant. They contain polarizabilities, form-factor information, resonance effects, and other details of the hard dynamics. The point of the theorem is that the first singular terms do not require such detailed knowledge.

## Real radiation and the infrared logarithm

The leading theorem immediately explains the soft infrared logarithm. The real-emission probability contains

$$
d\Pi_k |S_\gamma^{\rm lead}(k)|^2,
$$

where

$$
d\Pi_k
=
\frac{d^3\mathbf k}{(2\pi)^3 2\omega}
=
\frac{\omega\,d\omega\,d\Omega}{2(2\pi)^3}.
$$

Since

$$
S_\gamma^{\rm lead}(k)\sim\frac{1}{\omega},
$$

we get

$$
d\Pi_k |S_\gamma^{\rm lead}|^2
\sim
\frac{d\omega}{\omega}d\Omega.
$$

Thus the soft theorem predicts the logarithmic sensitivity

$$
\int_0^{\Delta E}\frac{d\omega}{\omega}
$$

that appears in real soft emission. The same universal soft factor controls the matching virtual soft singularity. Their cancellation in inclusive rates is the content of Bloch–Nordsieck and KLN physics.

## Example: soft photon in charged-scalar scattering

Consider charged scalar scattering

$$
a(p_1)+b(p_2)\to c(p_3)+d(p_4)
$$

with charges $Q_1,Q_2,Q_3,Q_4$. Add an unresolved photon of momentum $k$ to the final state. With $p_1,p_2$ incoming and $p_3,p_4$ outgoing, the leading soft theorem gives

$$
\mathcal M_5
\simeq
e\left[
-Q_1\frac{p_1\cdot\varepsilon^*}{p_1\cdot k}
-Q_2\frac{p_2\cdot\varepsilon^*}{p_2\cdot k}
+Q_3\frac{p_3\cdot\varepsilon^*}{p_3\cdot k}
+Q_4\frac{p_4\cdot\varepsilon^*}{p_4\cdot k}
\right]
\mathcal M_4.
$$

Replacing $\varepsilon^*$ by $k$ gives

$$
e(-Q_1-Q_2+Q_3+Q_4)\mathcal M_4,
$$

which vanishes precisely when the total incoming charge equals the total outgoing charge.

This example is a good way to debug signs. If the soft factor does not vanish under $\varepsilon\to k$, either charge conservation is violated or the incoming/outgoing sign convention has been applied inconsistently.

## Relation to asymptotic symmetries

The leading soft photon theorem has a modern interpretation as a Ward identity for large gauge transformations at null infinity. In that language, the theorem relates a low-energy photon insertion to the action of an asymptotic charge on the hard scattering states.

For the purposes of perturbative QFT, one does not need this interpretation to use the theorem. The external-line derivation and Ward identity already give the leading result. But the asymptotic-symmetry viewpoint explains why soft theorems, memory effects, and boundary charges are different faces of the same infrared structure.

This page keeps the amplitude-theory viewpoint. The asymptotic-symmetry and celestial-amplitude interpretations belong to later advanced pages.

## Common pitfalls

**Calling every low-energy photon theorem “Low's theorem.”** Low's theorem usually refers to the expansion through the subleading term. Weinberg's leading soft photon theorem is the universal $1/\omega$ factor.

**Forgetting the incoming/outgoing signs.** The sign $\eta_i$ is not optional bookkeeping. It is what turns the Ward-identity check into charge conservation.

**Applying the subleading operator to the wrong object.** The angular momentum operator should act on a stripped amplitude with a clear choice of independent external momenta.

**Ignoring collinear singularities.** The soft theorem controls $k^0\to0$. If charged external particles are massless, the limit can overlap with collinear singularities. Then soft and collinear factorization must be treated together.

**Assuming the soft theorem makes exclusive amplitudes observable.** The theorem explains the singular structure of amplitudes. Physical rates in theories with massless photons require inclusive measurements, dressed states, or another infrared-safe prescription.

**Overstating universality beyond the theorem's order.** The leading term is universal. The subleading term is universal under stated assumptions. Higher terms contain process-dependent structure.

## Relations to other pages

- [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/) derives the leading soft factor from external-line denominators and Wilson lines.
- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) explains how the leading theorem creates logarithmic infrared singularities in real radiation.
- [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/) explains how inclusive sums over unresolved photons cancel the corresponding virtual singularities.
- [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) gives the broader cancellation principle for soft and collinear degeneracies.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) gives the gauge-invariance identity whose soft limit becomes charge conservation.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) helps translate between incoming and outgoing external-leg conventions.

## Research status

- **Established:** The leading soft photon theorem follows from external-line poles and gauge invariance. Low's theorem gives the standard subleading result under analyticity and standard external-particle assumptions.
- **Active:** Infrared-finite charged-particle scattering, coherent-state dressings, asymptotic symmetries, memory effects, celestial amplitudes, loop corrections to subleading soft behavior, and soft expansions in massless theories are active areas.
- **Subtle:** The theorem is an expansion of regulated amplitudes or suitably defined matrix elements. In QED, the naive finite-particle S-matrix between Fock states has infrared problems; inclusive probabilities or dressed asymptotic states are needed for physical predictions.

## Exercises

### Exercise 1: Ward identity from the leading theorem

Use the leading soft photon theorem to show that replacing $\varepsilon^\mu$ by $k^\mu$ gives charge conservation.

<details>
<summary><strong>Solution</strong></summary>

The leading soft factor is

$$
S_\gamma^{\rm lead}
=
e\sum_i\eta_i Q_i\frac{p_i\cdot\varepsilon^*}{p_i\cdot k}.
$$

Replacing $\varepsilon^\mu$ by $k^\mu$ gives

$$
S_\gamma^{\rm lead}(k,k)
=
e\sum_i\eta_i Q_i\frac{p_i\cdot k}{p_i\cdot k}
=
e\sum_i\eta_i Q_i.
$$

The Ward identity requires this to vanish. Therefore

$$
\sum_i\eta_i Q_i=0,
$$

which says that the total incoming electric charge equals the total outgoing electric charge.

</details>

### Exercise 2: Soft factor for two-to-two scattering

For $e^-\mu^-\to e^-\mu^-$ plus one soft photon, write the leading soft factor using $Q_e=Q_\mu=-1$.

<details>
<summary><strong>Solution</strong></summary>

Let $p_1,p_2$ be incoming electron and muon momenta, and $p_3,p_4$ outgoing electron and muon momenta. Since all charges are $-1$,

$$
S_\gamma^{\rm lead}
=
e\left[
+\frac{p_1\cdot\varepsilon^*}{p_1\cdot k}
+\frac{p_2\cdot\varepsilon^*}{p_2\cdot k}
-\frac{p_3\cdot\varepsilon^*}{p_3\cdot k}
-\frac{p_4\cdot\varepsilon^*}{p_4\cdot k}
\right].
$$

The signs come from $\eta=-1$ for incoming and $\eta=+1$ for outgoing, multiplied by $Q=-1$ for each charged lepton.

Under $\varepsilon\to k$, this becomes

$$
e(1+1-1-1)=0,
$$

as required by charge conservation.

</details>

### Exercise 3: Soft logarithm

Use the leading scaling $S_\gamma^{\rm lead}\sim1/\omega$ and the massless phase-space measure to show that real soft emission has a logarithmic divergence.

<details>
<summary><strong>Solution</strong></summary>

For a massless photon,

$$
d\Pi_k
=
\frac{d^3\mathbf k}{(2\pi)^3 2\omega}
=
\frac{\omega\,d\omega\,d\Omega}{2(2\pi)^3}.
$$

The squared leading soft factor scales as

$$
|S_\gamma^{\rm lead}|^2\sim\frac{1}{\omega^2}.
$$

Thus

$$
d\Pi_k |S_\gamma^{\rm lead}|^2
\sim
\omega\,d\omega\,d\Omega\,\frac{1}{\omega^2}
=
\frac{d\omega}{\omega}d\Omega.
$$

The energy integral contains

$$
\int_0^{\Delta E}\frac{d\omega}{\omega},
$$

which is logarithmically divergent at $\omega=0$.

</details>

### Exercise 4: Subleading gauge check

Show that the displayed subleading soft factor is unchanged under $\varepsilon^\mu\to\varepsilon^\mu+\alpha k^\mu$.

<details>
<summary><strong>Solution</strong></summary>

The subleading factor is

$$
S_\gamma^{\rm sub}
=
-i e\sum_i\eta_i Q_i
\frac{\varepsilon_\mu^* k_\nu J_i^{\mu\nu}}{p_i\cdot k}.
$$

The shift $\varepsilon_\mu^*\to\varepsilon_\mu^*+\alpha k_\mu$ changes the numerator by

$$
\alpha k_\mu k_\nu J_i^{\mu\nu}.
$$

But $k_\mu k_\nu$ is symmetric in $\mu,\nu$, while $J_i^{\mu\nu}$ is antisymmetric. Therefore

$$
k_\mu k_\nu J_i^{\mu\nu}=0,
$$

so the subleading soft factor is gauge invariant by itself.

</details>

## References

- F. E. Low, “Bremsstrahlung of Very Low-Energy Quanta in Elementary Particle Collisions,” *Physical Review* **110** (1958), for the classic subleading soft photon result.
- T. H. Burnett and N. M. Kroll, “Extension of the Low Soft Photon Theorem,” *Physical Review Letters* **20** (1968), for the structure of soft radiation in cross sections.
- S. Weinberg, “Infrared Photons and Gravitons,” *Physical Review* **140** (1965), for the leading soft photon and graviton theorem and infrared consequences.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for soft photons, infrared divergences, and the relation to scattering theory.
- M. Srednicki, *Quantum Field Theory*, section 26, for a compact treatment of infrared divergences.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 20, for soft radiation and real–virtual cancellation in QED.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, with leading theorem, Low subleading structure, Ward-identity checks, infrared-log derivation, and solved exercises.
