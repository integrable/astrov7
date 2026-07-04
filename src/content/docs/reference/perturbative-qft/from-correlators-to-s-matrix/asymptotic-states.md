---
title: "Asymptotic States"
description: "How in and out particle states are defined, normalized, and used as the Hilbert-space input to scattering amplitudes."
sidebar:
  label: "Asymptotic States"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§2–5 and 10–11; Coleman 2019, chs. 7 and 11–14; Weinberg 1995, Vol. I, ch. 3; Schwartz 2014, chs. 5–6"
topics:
  - asymptotic states
  - in states
  - out states
  - scattering theory
  - Fock space
  - Møller operators
canonicalTopics:
  - asymptotic-states
  - in-out-states
  - scattering-state-normalization
  - moller-operators
researchStatus:
  established:
    - "The use of stable asymptotic particle states and Møller operators in scattering theory is textbook-standard when the theory has a suitable particle spectrum and well-defined scattering states."
  active:
    - "Massless gauge theories, confinement, unstable particles, curved spacetime, finite density, and nonperturbative questions require refined notions of asymptotic states or different observables."
---

## Summary

Scattering theory compares what a state looks like when its particles are far apart in the remote past with what it looks like when its particles are far apart in the remote future. These far-past and far-future particle states are called **asymptotic states**.

The basic objects are

$$
\mid \alpha,\mathrm{in}\rangle,
\qquad
\mid \beta,\mathrm{out}\rangle,
$$

where $\alpha$ and $\beta$ label collections of stable particles with definite momenta, spin or helicity labels, and internal quantum numbers. The scattering matrix element is their overlap:

$$
S_{\beta\alpha}
=
\langle \beta,\mathrm{out}\mid \alpha,\mathrm{in}\rangle.
$$

With the qft.org covariant normalization, one-particle states obey

$$
\langle \mathbf p',s'\mid \mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,
\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'},
$$

and multiparticle in/out states are built from the corresponding asymptotic creation operators.

The important caveat is that asymptotic states are not arbitrary field configurations at finite time. They are the stable particle states that the interacting theory approaches when the particles are separated by macroscopic distances. This distinction is what lets local correlators eventually become scattering amplitudes through LSZ reduction.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/), [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/), [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/), and [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/).

The Foundations pages [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) and [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) explain why stable one-particle poles are the correlator-side signal of asymptotic particles.

## Core idea

Particles in an interacting QFT are not generally free at finite times. Still, if the theory has stable particle species, then widely separated wave packets eventually stop interacting. The remote past and remote future therefore admit a free-particle description even though the middle of the process is fully interacting.

The conceptual flow is:

1. choose free Fock-space labels for incoming particles;
2. evolve them into the interacting theory from the far past;
3. let the exact interacting dynamics act;
4. compare the result with free Fock-space labels in the far future.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Incoming wave packets enter an interaction region and emerge as outgoing wave packets](/figures/perturbative-qft/asymptotic-states-scattering.svg)

<figcaption>

Asymptotic states are free-particle states only in the remote past or future. The interaction region is governed by the full Hamiltonian; the in and out labels record how the state looks when the particles are well separated.

</figcaption>
</figure>

The slogan is:

$$
\text{asymptotic states are free particle data attached to the interacting theory.}
$$

That sentence is doing work. It says neither that the interacting theory is free, nor that the free Fock space is irrelevant. Scattering uses the free Fock space as the language of preparation and detection.

## Setup and conventions

We work in flat four-dimensional Minkowski spacetime with the qft.org mostly-minus metric and plane waves $e^{-ip\cdot x}$. One-particle states are covariantly normalized:

$$
\langle \mathbf p',s'\mid \mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,
\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'}.
$$

The on-shell measure is

$$
d\Pi_p
=
\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=
\frac{d^4p}{(2\pi)^3}\theta(p^0)\delta(p^2-m^2).
$$

A normalized one-particle wave packet is written

$$
\mid \Psi\rangle
=
\sum_s\int d\Pi_p\,f_s(\mathbf p)\mid\mathbf p,s\rangle,
$$

with

$$
\langle\Psi\mid\Psi\rangle
=
\sum_s\int d\Pi_p\,|f_s(\mathbf p)|^2.
$$

Delta-normalized momentum eigenstates are idealizations. They are excellent for deriving compact formulas, but physical scattering is prepared and measured with wave packets or beams. The delta functions in $S$-matrix formulas are the infinite-volume remnant of this idealization.

## In and out states

Let $H$ be the full Hamiltonian and $H_0$ the free Hamiltonian associated with the stable particle species used to label asymptotic states. Formally, define the Møller operators

$$
\Omega_{\mathrm{in}}
=
\lim_{t\to-\infty}e^{iHt}e^{-iH_0t},
\qquad
\Omega_{\mathrm{out}}
=
\lim_{t\to+\infty}e^{iHt}e^{-iH_0t}.
$$

Then

$$
\mid\alpha,\mathrm{in}\rangle
=
\Omega_{\mathrm{in}}\mid\alpha\rangle_0,
\qquad
\mid\beta,\mathrm{out}\rangle
=
\Omega_{\mathrm{out}}\mid\beta\rangle_0,
$$

where $\mid\alpha\rangle_0$ and $\mid\beta\rangle_0$ are free Fock states. Equivalently, the exact time evolution of an in state looks free in the far past:

$$
e^{-iHt}\mid\alpha,\mathrm{in}\rangle
\sim
e^{-iH_0t}\mid\alpha\rangle_0
\qquad (t\to-\infty),
$$

and the exact time evolution of an out state looks free in the far future:

$$
e^{-iHt}\mid\beta,\mathrm{out}\rangle
\sim
e^{-iH_0t}\mid\beta\rangle_0
\qquad (t\to+\infty).
$$

The symbol $\sim$ is not an equality of local field configurations at finite time. It means equality in the scattering sense: after forming suitable wave packets, the difference between the exact interacting state and the corresponding free state becomes irrelevant in the asymptotic limit.

The S-matrix operator on free asymptotic labels is therefore

$$
S
=
\Omega_{\mathrm{out}}^\dagger\Omega_{\mathrm{in}},
$$

and its matrix elements are

$$
S_{\beta\alpha}
={}_0\langle\beta\mid S\mid\alpha\rangle_0
=
\langle\beta,\mathrm{out}\mid\alpha,\mathrm{in}\rangle.
$$

In most physics formulas the subscript $_0$ is suppressed; the state labels themselves tell you whether the states are in or out states.

:::caution[What this formalism assumes]
The Møller-operator definition is cleanest when the theory has stable particles, a good vacuum, and scattering states that span the relevant Hilbert-space sector. Long-range forces, massless particles, confinement, and unstable resonances require modifications or more careful observables.
:::

## Multiparticle labels

For distinguishable stable particles, a typical incoming state is labeled by

$$
\alpha=(p_1,s_1,a_1;\ldots;p_n,s_n,a_n),
$$

where $p_i^2=m_i^2$, $p_i^0>0$, $s_i$ is a spin or helicity label, and $a_i$ denotes internal quantum numbers such as charge, flavor, or color when color is an allowed asymptotic label.

In operator language, one writes schematically

$$
\mid p_1,s_1;\ldots;p_n,s_n,\mathrm{in}\rangle
=
a_{\mathrm{in}}^\dagger(p_1,s_1)\cdots
a_{\mathrm{in}}^\dagger(p_n,s_n)\mid0\rangle,
$$

and similarly for out states. For bosons the creation operators commute; for fermions they anticommute. For identical particles, the multiparticle state is automatically symmetrized or antisymmetrized by the creation-operator algebra.

For a set of identical bosons, writing a state as

$$
\mid p_1,p_2,\mathrm{in}\rangle
=
a_{\mathrm{in}}^\dagger(p_1)a_{\mathrm{in}}^\dagger(p_2)\mid0\rangle
$$

already includes the exchange symmetry. You should not add an extra hand-made symmetrization unless you have changed the normalization convention. This point becomes important when identical-particle factors appear in phase space.

## Stable particles and interpolating fields

Scattering amplitudes are matrix elements between particle states, but perturbation theory usually computes time-ordered correlators of fields. The bridge is an interpolating field with nonzero overlap with a stable one-particle state.

For a scalar particle of mass $m$, the exact two-point function has a pole

$$
G_2(p)
\underset{p^2\to m^2}{\sim}
\frac{iZ}{p^2-m^2+i\epsilon}
+
\text{regular},
$$

and the field has matrix element

$$
\langle0\mid\phi(0)\mid\mathbf p\rangle
=
\sqrt Z.
$$

The field $\phi$ is not the particle. It is a local operator that can create the particle from the vacuum with amplitude $\sqrt Z$, plus multiparticle contributions. LSZ reduction isolates the one-particle poles, removes the external propagators, and converts the connected correlator into an $S$-matrix element.

This is why asymptotic states are the right starting point for the chapter. Before asking how a correlator becomes an amplitude, one must know which particle states the amplitude is supposed to connect.

## Momentum conservation

Because the full Hamiltonian is translation invariant in flat spacetime, total four-momentum is conserved in scattering. If the incoming state has total momentum

$$
P_i=\sum_{a\in\mathrm{in}}p_a,
$$

and the outgoing state has total momentum

$$
P_f=\sum_{b\in\mathrm{out}}p_b,
$$

then nontrivial matrix elements contain

$$
(2\pi)^4\delta^{(4)}(P_f-P_i).
$$

This delta function is not a Feynman-rule decoration. It is the representation-theoretic statement that the $S$-matrix commutes with spacetime translations.

The invariant amplitude $\mathcal M$ is defined only after stripping off this total momentum-conserving delta function according to the convention in [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/).

## Where asymptotic states fail or need refinement

The clean in/out Fock-space picture is not universal.

**Unstable particles** are not asymptotic states. A resonance can appear as an intermediate pole or peak, but it does not label a stable incoming or outgoing state in the strict $S$-matrix.

**Confining theories** do not have colored quarks and gluons as asymptotic states. Perturbative QCD uses partonic amplitudes inside factorization theorems, but the physical asymptotic states are hadrons, photons, leptons, and other color-singlet objects.

**Massless gauge theories** have infrared subtleties. Charged particles are accompanied by long-range fields and arbitrarily soft radiation. Naive Fock states can be too exclusive; physical observables often require inclusive sums over unresolved radiation or dressed asymptotic states.

**Finite-temperature or finite-density systems** usually do not have the same vacuum-to-vacuum scattering interpretation. Response functions, spectral densities, transport coefficients, and in-medium quasiparticles replace the simple vacuum $S$-matrix as the central observables.

These caveats do not make the asymptotic-state formalism wrong. They say exactly where the simple version is allowed to be simple.

## Common pitfalls

**Treating an internal line as an asymptotic particle.** Internal lines are propagators integrated over off-shell momenta. Asymptotic states are external stable particles with on-shell momenta and Hilbert-space labels.

**Forgetting wave packets.** Delta-normalized momentum eigenstates are idealized. They make formulas compact, but wave packets are what justify statements about particles being separated at early and late times.

**Putting unstable particles in the external state list.** A resonance is not an exact in or out state. It is described by poles, widths, and decay products, not by a normalizable one-particle external state.

**Using colored partons as physical asymptotic states in confining QCD.** Partonic amplitudes are useful in high-energy factorization, but isolated colored states are not physical asymptotic states.

**Ignoring infrared degeneracy.** In theories with massless particles, a state with no soft radiation may be experimentally indistinguishable from a state with unresolved soft radiation. The observable must decide what is being summed over.

## Relations to other pages

- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) turns asymptotic-state overlaps into the $S=\mathbf 1+iT$ convention and the invariant amplitude $\mathcal M$.
- [Conventions and Notation](/perturbative-qft/conventions/) fixes the state normalization, on-shell measure, and amplitude convention used here.
- [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/) develops the covariant one-particle normalization and invariant measure.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) explains why stable particles appear as poles in exact two-point functions.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) gives the first correlator-side version of the asymptotic-state bridge.
- [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/) explains why scattering amplitudes focus on the connected part after the identity contribution is separated.

## Research status

The in/out-state formalism is standard scattering theory. Its cleanest version applies to stable particles in flat spacetime with well-separated wave packets and no unresolved long-range complications. The main active or subtle issues are not the basic definitions, but their refinement in gauge theories with infrared radiation, confining theories, nonperturbative settings, curved backgrounds, finite-density systems, and theories without conventional particle states.

## Exercises

### Exercise 1: Normalize a one-particle wave packet

Let

$$
\mid\Psi\rangle
=
\sum_s\int d\Pi_p\,f_s(\mathbf p)\mid\mathbf p,s\rangle.
$$

Using the covariant normalization of one-particle states, show that

$$
\langle\Psi\mid\Psi\rangle
=
\sum_s\int d\Pi_p\,|f_s(\mathbf p)|^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert the expansion on both sides:

$$
\langle\Psi\mid\Psi\rangle
=
\sum_{s,s'}\int d\Pi_{p'}d\Pi_p\,
f_{s'}(\mathbf p')^*f_s(\mathbf p)
\langle\mathbf p',s'\mid\mathbf p,s\rangle.
$$

Using

$$
\langle\mathbf p',s'\mid\mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'},
$$

and

$$
d\Pi_p=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}},
$$

the delta function removes one integral and one spin sum. The result is

$$
\langle\Psi\mid\Psi\rangle
=
\sum_s\int d\Pi_p\,|f_s(\mathbf p)|^2.
$$

</details>

### Exercise 2: Derive the Møller-operator expression for the S-matrix

Given

$$
\mid\alpha,\mathrm{in}\rangle=\Omega_{\mathrm{in}}\mid\alpha\rangle_0,
\qquad
\mid\beta,\mathrm{out}\rangle=\Omega_{\mathrm{out}}\mid\beta\rangle_0,
$$

show that

$$
S_{\beta\alpha}
={}_0\langle\beta\mid\Omega_{\mathrm{out}}^\dagger\Omega_{\mathrm{in}}\mid\alpha\rangle_0.
$$

<details>
<summary><strong>Solution</strong></summary>

Start from the definition of the scattering matrix element:

$$
S_{\beta\alpha}
=
\langle\beta,\mathrm{out}\mid\alpha,\mathrm{in}\rangle.
$$

Taking the adjoint of

$$
\mid\beta,\mathrm{out}\rangle=\Omega_{\mathrm{out}}\mid\beta\rangle_0
$$

gives

$$
\langle\beta,\mathrm{out}\mid
={}_0\langle\beta\mid\Omega_{\mathrm{out}}^\dagger.
$$

Substituting both in and out definitions gives

$$
S_{\beta\alpha}
={}_0\langle\beta\mid\Omega_{\mathrm{out}}^\dagger\Omega_{\mathrm{in}}\mid\alpha\rangle_0.
$$

Thus the operator acting on free asymptotic labels is

$$
S=\Omega_{\mathrm{out}}^\dagger\Omega_{\mathrm{in}}.
$$

</details>

### Exercise 3: Momentum conservation from translations

Suppose the $S$-matrix commutes with spacetime translations, so that

$$
[P^\mu,S]=0.
$$

Show that a matrix element between total momentum eigenstates vanishes unless $P_f=P_i$.

<details>
<summary><strong>Solution</strong></summary>

Let

$$
P^\mu\mid i\rangle=P_i^\mu\mid i\rangle,
\qquad
P^\mu\mid f\rangle=P_f^\mu\mid f\rangle.
$$

Taking the matrix element of $[P^\mu,S]=0$ gives

$$
0=\langle f\mid[P^\mu,S]\mid i\rangle
=(P_f^\mu-P_i^\mu)\langle f\mid S\mid i\rangle.
$$

Therefore, if $P_f^\mu\ne P_i^\mu$, the matrix element must vanish. In continuum normalization this selection rule appears as the factor

$$
(2\pi)^4\delta^{(4)}(P_f-P_i).
$$

</details>

### Exercise 4: Why resonances are not external states

Explain why an unstable particle of width $\Gamma>0$ should not be treated as an exact asymptotic external state.

<details>
<summary><strong>Solution</strong></summary>

An exact asymptotic external state must survive to $t\to\pm\infty$ as a stable particle label. An unstable particle decays, so a wave packet prepared as that resonance does not remain a one-particle state at arbitrarily late times.

In correlators and amplitudes, the unstable particle usually appears as a pole shifted away from the real axis or as a resonant enhancement in amplitudes involving its decay products. The proper external states are the stable particles that enter and leave the detector.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§2–5 and §§10–11, for relativistic normalization, LSZ, amplitudes, and cross sections.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 7 and 11–14, for scattering, in/out states, Green functions, and LSZ.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5–6, for cross sections, decay rates, and the S-matrix/LSZ bridge.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for a systematic scattering-theory construction of in states, out states, the S-matrix, rates, and unitarity.
- R. Haag, *Local Quantum Physics*, for the more structural viewpoint on scattering, locality, and the subtleties behind asymptotic completeness.

## Version history

- **2026-06-12:** Initial standardized page.
