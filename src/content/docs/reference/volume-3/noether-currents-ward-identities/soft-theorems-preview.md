---
title: "Soft Theorems Preview"
description: "Introduces soft theorems as Ward identities for low-energy massless particles, with leading photon, gluon, graviton, and Goldstone examples."
sidebar:
  label: "Soft Theorems Preview"
  order: 10
level: Advanced
status: "Polished draft"
source: "Coleman Aspects of Symmetry on soft pions; Low and Weinberg on soft photons and gravitons; modern asymptotic-symmetry perspective from Strominger and related reviews."
topics:
  - soft theorems
  - Ward identities
  - infrared physics
  - soft photons
  - soft gravitons
  - soft pions
  - asymptotic symmetries
canonicalTopics:
  - soft-theorem
  - soft-photon-theorem
  - soft-graviton-theorem
  - asymptotic-symmetry-ward-identity
  - infrared-factorization
researchStatus:
  established:
    - "Leading soft photon and soft graviton factorization are standard consequences of gauge invariance, locality, and the universal coupling of massless gauge fields to conserved charges or stress tensors."
  active:
    - "The relation among soft theorems, asymptotic symmetries, memory effects, celestial descriptions, loop corrections, and EFT deformations remains an active research area."
---

## Summary

A soft theorem describes what happens to an amplitude when one external particle becomes very low energy. For a photon with momentum $q^\mu\to 0$, the leading soft theorem says schematically

$$
\mathcal M_{n+1}(q,\varepsilon;p_1,\ldots,p_n)
=
\left[e\sum_{k=1}^n\eta_k Q_k\frac{p_k\cdot\varepsilon}{p_k\cdot q}\right]
\mathcal M_n(p_1,\ldots,p_n)
+O(q^0).
$$

The bracket is the **soft factor**. It is universal: it depends only on the soft photon's polarization and momentum, and on the hard external particles' momenta and charges. It does not know the detailed short-distance interaction that produced the hard scattering.

For a graviton, the leading soft factor is even more universal:

$$
\mathcal M_{n+1}(q,\varepsilon_{\mu\nu};p_1,\ldots,p_n)
=
\left[\frac{\kappa}{2}\sum_{k=1}^n\eta_k
\frac{p_k^\mu p_k^\nu\varepsilon_{\mu\nu}}{p_k\cdot q}\right]
\mathcal M_n(p_1,\ldots,p_n)
+O(q^0).
$$

This page is only a preview because a full treatment belongs partly to scattering theory, partly to infrared physics, partly to asymptotic symmetry, and partly to gauge theory and gravity. The reason it appears here is conceptual: many soft theorems are Ward identities in disguise.

<figure class="doc-figure" style="--figure-width: 45rem;">

![A hard amplitude with a soft gauge boson attached to each external leg. In the soft limit the sum of external emissions factorizes into a universal soft factor times the hard amplitude.](/figures/symmetry-anomalies-topology/soft-factorization-external-legs.svg)

<figcaption>

In the leading soft limit, emission from external hard legs dominates. The sum over external attachments factorizes into a universal soft factor multiplying the hard amplitude. Ward identities and gauge invariance determine the universal structure.

</figcaption>
</figure>

The moral is:

$$
\text{soft theorem}
\quad\approx\quad
\text{Ward identity for a long-wavelength symmetry charge}.
$$

The symbol $\approx$ is deliberate. Turning this slogan into a theorem requires careful choices of asymptotic states, infrared regulators, inclusive observables, boundary conditions, and sometimes spacetime dimension.

## Prerequisites

Read [Ward Identities: Operator Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-operator-form/), [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/), [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/), and [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/) first.

You should also know the basic idea of scattering amplitudes and external particles. The full derivation uses LSZ reduction, gauge-field propagators, and infrared regularization, which are developed in the Perturbative QFT and Scattering volume.

## Core idea

A very low-energy massless particle has a long wavelength. It cannot resolve the short-distance details of the hard interaction. It mainly sees conserved charges, momenta, and angular momenta carried by the external particles.

That is why soft factors are universal.

For a soft photon, the long-wavelength field couples to electric charge. For a soft gluon, it couples to color charge, with nonabelian ordering. For a soft graviton, it couples to energy-momentum. For a soft Goldstone boson, it probes a spontaneously broken current. These are all symmetry statements, but the details differ.

The basic mechanisms are:

| Soft particle | Symmetry data it probes | Typical leading behavior |
|---|---|---|
| photon | electric charge | $1/\omega$ |
| gluon | color generator | $1/\omega$ with ordering/color structure |
| graviton | energy-momentum | $1/\omega$ |
| Goldstone boson | broken current | often $\omega^0$ or vanishing Adler zero, depending on the theory and process |

Here $\omega$ is the soft particle energy. Gauge bosons and gravitons have pole-like soft factors because the soft particle can attach to external on-shell lines. Goldstone soft limits are governed by broken-current Ward identities and have different kinematics.

## Setup and conventions

We work in mostly-minus Lorentzian signature and use the scattering-amplitude convention that all hard external momenta are on shell.

For the displayed photon and graviton formulas:

- $q^\mu$ is the soft momentum and $q^\mu\to 0$.
- $\varepsilon_\mu(q)$ is a photon polarization satisfying $q\cdot\varepsilon=0$.
- $\varepsilon_{\mu\nu}(q)$ is a graviton polarization, symmetric, transverse, and traceless in a physical gauge.
- $p_k^\mu$ are the hard external momenta.
- $Q_k$ is the electric charge of hard external particle $k$ in units of $e$.
- $\eta_k=+1$ for outgoing hard particles and $\eta_k=-1$ for incoming hard particles.
- $\kappa$ is the gravitational coupling, often normalized by $\kappa^2=32\pi G$.

The soft limit is an expansion in $q$ with hard momenta held fixed away from collinear singularities. If massless hard particles are present, soft and collinear limits can overlap; then a more careful factorization framework is needed.

:::note[Convention-sensitive source note]
Soft-theorem signs depend on whether all momenta are taken outgoing, whether incoming particles are crossed to outgoing antiparticles, and how electric charges are assigned under crossing. This page uses the explicit $\eta_k$ convention above. Many amplitude papers instead take all momenta outgoing, absorbing $\eta_k$ into the crossed momenta and charges.
:::

## Leading soft photons

Consider an amplitude with $n$ hard external charged particles and one extra photon of soft momentum $q$. The leading soft photon theorem is

$$
\mathcal M_{n+1}(q,\varepsilon;p_1,\ldots,p_n)
=S_\gamma^{(0)}(q,\varepsilon)\mathcal M_n(p_1,\ldots,p_n)+O(q^0),
$$

where

$$
S_\gamma^{(0)}(q,\varepsilon)
=e\sum_{k=1}^n\eta_k Q_k\frac{p_k\cdot\varepsilon}{p_k\cdot q}.
$$

The pole $1/(p_k\cdot q)$ has a simple origin. If the soft photon is emitted from an external charged leg, the nearby propagator carries momentum $p_k+\eta_k q$. Since $p_k^2=m_k^2$ and $q^2=0$,

$$
(p_k+\eta_k q)^2-m_k^2
=2\eta_k p_k\cdot q+O(q^2).
$$

Thus the external-line diagram has a soft pole. Emission from internal lines is less singular because generic internal momenta are off shell. Therefore the leading soft behavior is controlled by external particles.

The numerator is also universal. At leading order the soft photon couples eikonally to the hard particle momentum and charge, giving $eQ_k p_k\cdot\varepsilon$ for a scalar or the same leading factor for higher spin after using the on-shell equations of motion.

The result is the soft factor above.

## Gauge invariance and charge conservation

The soft photon formula knows about charge conservation.

Gauge invariance says the amplitude should vanish if the photon polarization is replaced by a pure gauge polarization,

$$
\varepsilon_\mu\mapsto q_\mu.
$$

Under this replacement,

$$
S_\gamma^{(0)}(q,q)
=e\sum_{k=1}^n\eta_k Q_k\frac{p_k\cdot q}{p_k\cdot q}
=e\sum_{k=1}^n\eta_k Q_k.
$$

Therefore gauge invariance requires

$$
\sum_{k=1}^n\eta_k Q_k=0.
$$

This is precisely conservation of total electric charge between the incoming and outgoing hard states.

This is the first hint that soft theorems are Ward identities. The pure-gauge polarization tests the symmetry charge. The consistency of the soft factor is equivalent to conservation of that charge.

## Leading soft gravitons

For gravity, the leading soft graviton theorem is

$$
\mathcal M_{n+1}(q,\varepsilon_{\mu\nu};p_1,\ldots,p_n)
=S_g^{(0)}(q,\varepsilon)\mathcal M_n(p_1,\ldots,p_n)+O(q^0),
$$

with

$$
S_g^{(0)}(q,\varepsilon)
=\frac{\kappa}{2}\sum_{k=1}^n\eta_k
\frac{p_k^\mu p_k^\nu\varepsilon_{\mu\nu}}{p_k\cdot q}.
$$

The structure parallels the photon case, but the charge is replaced by momentum. This is the equivalence principle in amplitude form: a soft graviton couples universally to stress-energy, not to a model-dependent charge.

Gauge invariance for a graviton is linearized diffeomorphism invariance. A pure-gauge shift has the form

$$
\varepsilon_{\mu\nu}\mapsto \varepsilon_{\mu\nu}+q_\mu\xi_\nu+q_\nu\xi_\mu,
$$

up to conventional factors. Applying this to the leading soft factor gives a term proportional to

$$
\sum_{k=1}^n\eta_k p_k^\mu.
$$

Thus gauge invariance requires

$$
\sum_{k=1}^n\eta_k p_k^\mu=0,
$$

which is total energy-momentum conservation.

The analogy is clean:

$$
\begin{array}{c|c|c}
\text{soft particle} & \text{pure gauge test} & \text{conservation law} \\
\hline
\gamma & \varepsilon_\mu\to q_\mu & \sum \eta_k Q_k=0 \\
g_{\mu\nu} & \varepsilon_{\mu\nu}\to q_{(\mu}\xi_{\nu)} & \sum \eta_k p_k^\mu=0
\end{array}
$$

## Soft gluons

For nonabelian gauge theory, a soft gluon also factorizes at leading order, but the soft factor is an operator on the color indices of the hard amplitude:

$$
S_{\text{gluon}}^{(0),a}(q,\varepsilon)
=g\sum_{k=1}^n\eta_k\frac{p_k\cdot\varepsilon}{p_k\cdot q}\,T_k^a.
$$

Here $T_k^a$ acts on the color representation of external leg $k$. The soft theorem is no longer just multiplication by a number; it inserts a color generator into the hard amplitude.

Gauge invariance now tests color-charge conservation:

$$
\sum_{k=1}^n\eta_kT_k^a\,\mathcal M_n=0,
$$

which is the nonabelian Ward identity for a color-singlet physical amplitude. In practice, nonabelian soft limits are intertwined with color ordering, multiple-soft ordering, Wilson lines, and infrared factorization.

This is why nonabelian soft theorems are a preview here rather than a full topic. The conceptual seed is the same as for photons: the soft gauge boson sees the symmetry charge carried by hard external particles.

## Soft Goldstone bosons and Adler zeros

Soft Goldstone bosons are controlled by a different but closely related mechanism.

If a continuous global symmetry is spontaneously broken, there is a conserved current $j_a^\mu$ and a Goldstone field $\pi^a$ that couples to it. The current has a one-particle matrix element of the schematic form

$$
\langle 0|j_a^\mu(0)|\pi^b(q)\rangle
=i f_\pi q^\mu\delta_a{}^b.
$$

A Ward identity for the broken current can then be converted, using LSZ, into a statement about amplitudes with one soft Goldstone boson.

In many familiar cases, amplitudes involving a single soft pion vanish as the pion momentum goes to zero. This is the Adler zero:

$$
\mathcal M_{n+1}(\pi(q);p_1,\ldots,p_n)\to 0
\qquad\text{as }q\to 0,
$$

under assumptions about the external states and absence of singular terms.

Do not confuse this with the photon or graviton $1/\omega$ pole. A Goldstone boson is not a gauge boson attached to external charged lines through an eikonal pole. It is the excitation created by a broken global current. Its soft behavior reflects nonlinear symmetry realization.

This is why soft-pion theorems live naturally near spontaneous symmetry breaking, current algebra, and Ward identities. Coleman-style current algebra was historically one of the cleanest ways to understand them.

## Ward identity viewpoint

A Ward identity says that inserting the divergence of a current is equivalent to acting with the charge on other insertions:

$$
\partial_\mu\langle T\,j^\mu(x)\mathcal X\rangle
=\text{contact terms}.
$$

To get a soft theorem, one Fourier transforms the current insertion and studies small momentum $q$:

$$
\int d^dx\,e^{iq\cdot x}\partial_\mu\langle T\,j^\mu(x)\mathcal X\rangle
=-iq_\mu\langle \widetilde j^\mu(q)\mathcal X\rangle.
$$

If $\widetilde j^\mu(q)$ has a pole associated with a massless particle, LSZ relates that pole to an amplitude with an external soft particle. The contact terms on the right side become the charge action on the hard external insertions. This is the schematic chain:

$$
\text{current Ward identity}
\quad\Longrightarrow\quad
\text{small-}q\text{ current insertion}
\quad\Longrightarrow\quad
\text{soft external particle theorem}.
$$

This derivation is cleanest when the relevant massless pole is isolated and infrared subtleties are controlled.

## Asymptotic symmetries and large charges

For photons and gravitons in four-dimensional asymptotically flat spacetime, the modern story sharpens the Ward-identity viewpoint.

Gauge transformations that approach nonzero angle-dependent functions at null infinity can act as physical asymptotic symmetries. Their charges contain two kinds of pieces:

$$
Q=Q_{\text{hard}}+Q_{\text{soft}}.
$$

The hard part acts on finite-energy charged particles. The soft part creates or annihilates zero-energy gauge bosons or gravitons. The Ward identity

$$
\langle \text{out}|\left(Q^+S-SQ^-\right)|\text{in}\rangle=0
$$

then becomes a soft theorem.

The same pattern appears in the so-called infrared triangle:

$$
\text{soft theorem}
\quad\Longleftrightarrow\quad
\text{asymptotic symmetry}
\quad\Longleftrightarrow\quad
\text{memory effect}.
$$

This triangle is an active and beautiful subject, but it should not be retroactively imposed on every soft theorem. The safe statement is narrower: many leading and subleading soft theorems can be interpreted as Ward identities of asymptotic or generalized symmetry charges, once the infrared setup is specified carefully.

## Infrared divergences and what amplitudes mean

Soft theorems are often stated as equations for amplitudes, but amplitudes with massless photons or gravitons can be infrared divergent.

In QED, the emission of arbitrarily low-energy photons is experimentally unavoidable. A detector has finite energy resolution, so physical predictions are inclusive: one sums over unobserved photons below a resolution scale. Virtual soft photons also contribute infrared divergences. The inclusive rate is finite after real and virtual soft effects are combined.

This does not make the soft theorem wrong. It means that the object being factorized must be defined with an infrared regulator, dressed states, or inclusive observables. A clean amplitude-level formula is a local statement about the leading behavior before the final infrared-safe observable is assembled.

The same warning is even sharper in gravity, where soft gravitons are also unavoidable and the asymptotic Hilbert space has delicate structure.

## What is universal and what is not

Soft theorems come in leading, subleading, and sub-subleading versions. Their universality varies.

The leading photon and graviton factors are highly universal. They follow from gauge invariance, locality, and the universal coupling to conserved charges or stress tensors.

Subleading terms are more delicate. They can involve angular momentum operators, spin, magnetic moments, higher-dimension operators, loop corrections, and dimension-dependent effects. In some theories they are universal at tree level but corrected at loop level. In effective field theory, higher-derivative interactions can deform subleading soft behavior.

Goldstone soft theorems depend on the symmetry breaking pattern and on whether the Goldstone interactions are derivatively coupled, whether there are singular exchange diagrams, and whether the symmetry is internal, spacetime, supersymmetric, or enhanced.

So the right habit is:

$$
\text{state the soft limit, the particle, the dimension, the loop order, and the assumptions.}
$$

A slogan without its assumptions is just a future erratum wearing sunglasses.

## Common pitfalls

**Pitfall 1: Treating every soft theorem as a photon theorem.** Soft photons, soft gluons, soft gravitons, and soft Goldstone bosons have different symmetry origins and different leading powers.

**Pitfall 2: Forgetting incoming signs.** If some particles are incoming, either use the explicit $\eta_k$ convention or cross everything to outgoing particles. Mixing conventions gives fake violations of charge conservation.

**Pitfall 3: Ignoring infrared divergences.** In theories with massless gauge bosons or gravitons, amplitude-level formulas often require an infrared regulator or a dressed-state/inclusive-observable interpretation.

**Pitfall 4: Confusing soft and collinear limits.** A soft limit sends energy to zero. A collinear limit makes two momenta parallel. For massless particles these limits can overlap, but they are not the same.

**Pitfall 5: Assuming subleading universality without checking assumptions.** Leading factors are robust; subleading factors are more sensitive to spin, loops, higher-derivative interactions, and dimension.

**Pitfall 6: Calling gauge redundancy a global symmetry too quickly.** The asymptotic-symmetry interpretation involves large transformations and boundary charges. Bulk gauge redundancy by itself is not a physical global symmetry.

## Relations to other pages

- [Ward Identities: Operator Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-operator-form/) gives the charge-conservation identity that soft theorems refine in momentum space.
- [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/) explains how current contact terms become charge actions on hard insertions.
- [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/) is the classic home of soft-pion reasoning.
- [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/) develops Goldstone bosons and broken-current Ward identities.
- [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) explains the source and gauge-field viewpoint behind Ward identities.
- The Perturbative QFT and Scattering volume develops LSZ, amplitudes, external-leg factorization, infrared divergences, and inclusive observables.
- The Spacetime, Gravity, and Holography volume develops BMS symmetry, memory effects, and gravitational soft theorems.

## Research status

Leading soft photon and soft graviton theorems are established parts of perturbative QFT. Their relation to gauge invariance and conservation laws is textbook-level physics.

The broader web connecting soft theorems, asymptotic symmetries, memory effects, celestial CFT, loop corrections, effective operators, and nonperturbative infrared sectors is active research. The modern asymptotic-symmetry program has turned soft theorems from useful scattering identities into probes of the infrared structure of gauge theory and gravity.

For this volume, the key point is conceptual rather than encyclopedic: soft theorems are among the most concrete places where Ward identities directly constrain observable scattering data.

## Exercises

### Exercise 1: Gauge invariance of the soft photon factor

Starting from

$$
S_\gamma^{(0)}=e\sum_{k=1}^n\eta_k Q_k\frac{p_k\cdot\varepsilon}{p_k\cdot q},
$$

show that invariance under $\varepsilon_\mu\to\varepsilon_\mu+\lambda q_\mu$ requires total charge conservation.

<details><summary><strong>Solution</strong></summary>

Under the shift,

$$
\Delta S_\gamma^{(0)}
=e\sum_k\eta_k Q_k\frac{p_k\cdot(\lambda q)}{p_k\cdot q}
=e\lambda\sum_k\eta_k Q_k.
$$

For the amplitude to be invariant for arbitrary $\lambda$, we need

$$
\sum_k\eta_k Q_k=0.
$$

This is the statement that total outgoing charge equals total incoming charge.

</details>

### Exercise 2: The external-line soft pole

Let a scalar external particle have on-shell momentum $p$ with $p^2=m^2$. A soft photon of momentum $q$ is emitted from this line. Show that the adjacent propagator has a denominator proportional to $p\cdot q$.

<details><summary><strong>Solution</strong></summary>

The adjacent propagator carries momentum $p+q$ for an outgoing emission convention. Its denominator is

$$
(p+q)^2-m^2=p^2+2p\cdot q+q^2-m^2.
$$

Using $p^2=m^2$ and $q^2=0$ for a photon,

$$
(p+q)^2-m^2=2p\cdot q.
$$

Thus the propagator scales as

$$
\frac{1}{2p\cdot q},
$$

which produces the leading soft pole.

</details>

### Exercise 3: Graviton gauge invariance and momentum conservation

Use

$$
S_g^{(0)}=\frac{\kappa}{2}\sum_k\eta_k
\frac{p_k^\mu p_k^\nu\varepsilon_{\mu\nu}}{p_k\cdot q}
$$

and the pure-gauge shift

$$
\varepsilon_{\mu\nu}\to \varepsilon_{\mu\nu}+q_\mu\xi_\nu+q_\nu\xi_\mu
$$

to show that gauge invariance requires momentum conservation.

<details><summary><strong>Solution</strong></summary>

The change in the soft factor is

$$
\Delta S_g^{(0)}
=\frac{\kappa}{2}\sum_k\eta_k
\frac{p_k^\mu p_k^\nu(q_\mu\xi_\nu+q_\nu\xi_\mu)}{p_k\cdot q}.
$$

The two terms are equal, so

$$
\Delta S_g^{(0)}
=\kappa\sum_k\eta_k
\frac{(p_k\cdot q)(p_k\cdot\xi)}{p_k\cdot q}
=\kappa\xi_\mu\sum_k\eta_kp_k^\mu.
$$

For arbitrary $\xi_\mu$, gauge invariance requires

$$
\sum_k\eta_kp_k^\mu=0.
$$

This is total energy-momentum conservation.

</details>

### Exercise 4: Abelian versus nonabelian soft factors

Explain why the photon soft factor multiplies the hard amplitude by a number, while the gluon soft factor acts as an operator on the hard amplitude.

<details><summary><strong>Solution</strong></summary>

In QED the charge $Q_k$ of external leg $k$ is an abelian number. Therefore

$$
S_\gamma^{(0)}=e\sum_k\eta_k Q_k\frac{p_k\cdot\varepsilon}{p_k\cdot q}
$$

is a scalar factor multiplying $\mathcal M_n$.

In a nonabelian gauge theory, the color charge of leg $k$ is represented by a matrix or generator $T_k^a$ acting on that leg's color index. Hence

$$
S_{\text{gluon}}^{(0),a}=g\sum_k\eta_k\frac{p_k\cdot\varepsilon}{p_k\cdot q}T_k^a
$$

acts on the color vector or tensor structure of the hard amplitude. It is not merely a number.

</details>

## References

- F. E. Low, “Bremsstrahlung of Very Low-Energy Quanta in Elementary Particle Collisions,” *Physical Review* **110** (1958). Classic low-energy photon theorem.
- Steven Weinberg, “Infrared Photons and Gravitons,” *Physical Review* **140** (1965). Classic leading soft photon and graviton factorization.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions,” for current algebra and soft-pion theorems.
- Mark Srednicki, *Quantum Field Theory*, especially the Ward-identity and infrared-divergence sections.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially Ward–Takahashi identities, infrared divergences, and gauge-theory scattering.
- Andrew Strominger, *Lectures on the Infrared Structure of Gravity and Gauge Theory*, for the modern relation between soft theorems, memory effects, and asymptotic symmetries.
- Zvi Bern, Scott Davies, Paolo Di Vecchia, and Josh Nohle, “Low-Energy Behavior of Gluons and Gravitons from Gauge Invariance,” for modern tree-level soft-gluon and soft-graviton perspectives.

## Version history

- **2026-06-17:** Initial polished preview introducing leading soft photon, gluon, graviton, and Goldstone soft behavior as Ward-identity constraints, with infrared and asymptotic-symmetry caveats.
