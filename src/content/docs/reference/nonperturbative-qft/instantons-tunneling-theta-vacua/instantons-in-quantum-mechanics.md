---
title: "Instantons in Quantum Mechanics"
description: "Derives the Euclidean instanton calculation in one-dimensional quantum mechanics, using the double-well and periodic potentials as the prototype for tunneling effects."
sidebar:
  label: "Instantons in QM"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman; Zinn-Justin; Mariño; Shifman; standard WKB treatments."
topics:
  - instantons
  - quantum mechanics
  - tunneling
  - double-well potential
  - periodic potential
  - dilute instanton gas
  - energy splitting
canonicalTopics:
  - nonperturbative-qft
  - instantons
  - semiclassical-methods
  - tunneling
researchStatus:
  established:
    - "The Euclidean instanton method gives the leading exponentially small tunneling effects in one-dimensional quantum mechanics when the semiclassical expansion is controlled."
  active:
    - "The same examples remain useful as laboratories for resurgence, exact WKB, complex saddles, and the relation between perturbative and nonperturbative sectors."
---

## Summary

Quantum mechanics is the cleanest laboratory for instantons. There is only one coordinate $q$, the Euclidean path integral is an ordinary path integral over functions $q(\tau)$, and the physical question is familiar: how can a particle tunnel through a barrier that no real-time classical trajectory crosses?

For a Hamiltonian

$$
H=\frac{p^2}{2}+V(q),
$$

the Euclidean action is

$$
S_E[q]=\int d\tau\left[\frac12\dot q^2+V(q)\right],
$$

and Euclidean saddle points obey

$$
\ddot q=V'(q).
$$

An **instanton** in quantum mechanics is a finite-action Euclidean solution that starts near one classical minimum as $\tau\to -\infty$ and ends near another as $\tau\to +\infty$. In a symmetric double well, it gives the leading splitting between the two lowest states. In a periodic potential, it gives the leading width of the lowest Bloch band.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A double-well potential and its Euclidean instanton path, showing tunneling between two classically degenerate minima.](/figures/nonperturbative-qft/qm-instanton-double-well.svg)

<figcaption>

The Euclidean instanton converts tunneling into classical motion in imaginary time. In the double-well example, the path $q_I(\tau)$ interpolates from one minimum to the other. Translating its center $\tau_0$ costs no action, producing a zero mode and a collective-coordinate integral.

</figcaption>
</figure>

The important lesson is not the exact numerical prefactor of a particular potential. It is the structure

$$
\text{tunneling effect}
\sim
K e^{-A/g}\left(1+O(g)\right),
$$

where $A$ is the classical instanton action and $K$ is a one-loop determinant and zero-mode factor. The factor $e^{-A/g}$ is invisible to ordinary perturbation theory around either minimum. That invisibility is the baby version of what will later happen in Yang–Mills theory, theta vacua, and resurgence.

## Prerequisites

You should know [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), and [Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/).

It also helps to have read [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/), because the instanton contribution is the canonical example of a term that is smaller than every power of the coupling.

## Core idea

Ordinary perturbation theory around a classical minimum is local. It expands the potential in a Taylor series near that minimum and builds oscillator corrections. If the potential has two well-separated minima, perturbation theory around the left well cannot know that the right well exists. The Taylor series around $q=-v$ has no memory of the separate Taylor series around $q=+v$.

Quantum mechanics does know. The true eigenstates are spread across configuration space. In a symmetric double well, the two perturbative ground states localized near the two minima mix. The approximate left and right states $|L\rangle$ and $|R\rangle$ combine into parity eigenstates

$$
|+\rangle\simeq \frac{|L\rangle+|R\rangle}{\sqrt2},
\qquad
|-\rangle\simeq \frac{|L\rangle-|R\rangle}{\sqrt2}.
$$

The energy splitting is exponentially small,

$$
\Delta E=E_- - E_+ \sim e^{-A/g},
$$

where $g$ is the semiclassical parameter. This is not a high order in perturbation theory. It is a different sector of the semiclassical expansion.

The Euclidean path integral sees the effect because imaginary time turns the tunneling problem into an ordinary saddle-point problem. The instanton is a classical Euclidean path that crosses the barrier. In real time, the barrier is forbidden; in Euclidean time, the sign of the potential term in the mechanical analogy is reversed.

## Setup and conventions

We use units with $\hbar=1$. For the conceptual derivation, take

$$
H=\frac{p^2}{2}+V(q),
$$

with Euclidean transition amplitude

$$
\langle q_f|e^{-T H}|q_i\rangle
=
\int_{q(-T/2)=q_i}^{q(T/2)=q_f}\mathcal D q\,e^{-S_E[q]},
$$

where

$$
S_E[q]
=
\int_{-T/2}^{T/2}d\tau
\left[\frac12\dot q^2+V(q)\right].
$$

When we want an explicit small parameter, we write instead

$$
S_E[q]
=
\frac1g\int d\tau
\left[\frac12\dot q^2+U(q)\right],
\qquad
0<g\ll 1.
$$

Then the saddle action is $A/g$, with

$$
A=\int d\tau\left[\frac12\dot q_I^2+U(q_I)\right].
$$

Different books put the small parameter into the mass, the potential, or the coordinate rescaling. The physics is the same: the instanton contribution has an essential singularity at $g=0$.

We usually normalize the degenerate minima so that

$$
U(q_\pm)=0.
$$

This removes an irrelevant constant from the Euclidean action and makes finite-action boundary conditions simple:

$$
q(\tau)\to q_-
\quad (\tau\to -\infty),
\qquad
q(\tau)\to q_+
\quad (\tau\to +\infty).
$$

## Euclidean equations and the first integral

The Euclidean equation of motion follows from varying $S_E$:

$$
\ddot q=U'(q).
$$

This looks like Newton's equation in the **inverted potential** $-U(q)$. The conserved Euclidean mechanical energy is

$$
E_E=\frac12\dot q^2-U(q).
$$

For an instanton connecting degenerate minima with $U(q_\pm)=0$ and $\dot q\to0$ at both ends, this conserved quantity vanishes:

$$
E_E=0.
$$

Therefore the instanton obeys the first-order equation

$$
\frac12\dot q^2=U(q).
$$

Choosing the instanton orientation from $q_-$ to $q_+$ gives

$$
\dot q=+\sqrt{2U(q)}.
$$

The anti-instanton has the opposite sign.

This first-order equation is the quantum-mechanics ancestor of the BPS-like first-order equations that appear in solitons and Yang–Mills instantons. Here it is just energy conservation in Euclidean mechanics.

The instanton action simplifies:

$$
A
=
\int d\tau\left[\frac12\dot q^2+U(q)\right]
=
\int d\tau\,\dot q^2
=
\int_{q_-}^{q_+}dq\,\sqrt{2U(q)}.
$$

This formula is worth memorizing. It says that the leading exponential is an area under the Euclidean momentum curve.

## Example: the dimensionless double well

Take

$$
U(q)=\frac12(q^2-1)^2.
$$

The minima are $q_-= -1$ and $q_+=+1$. The first-order instanton equation is

$$
\dot q=1-q^2,
$$

whose solution is

$$
q_I(\tau)=\tanh(\tau-\tau_0).
$$

The parameter $\tau_0$ is arbitrary. It is the center of the tunneling event. Translating the instanton in Euclidean time does not change the action, so $\tau_0$ is a collective coordinate.

The action is

$$
A
=
\int_{-1}^{1}dq\,(1-q^2)
=\frac43.
$$

With the semiclassical normalization $S_E=A/g$, the leading exponential is

$$
e^{-4/(3g)}.
$$

Do not get too attached to the number $4/3$. It depends on how the double-well potential is scaled. The invariant statement is that $A$ is the Euclidean action of the finite-action path connecting the two minima.

## From one instanton to energy splitting

Let $K_{+-}(T)$ be the Euclidean transition amplitude from the left minimum to the right minimum over a long Euclidean time $T$:

$$
K_{+-}(T)
=
\langle q_+|e^{-T H}|q_-\rangle.
$$

Perturbation theory around either constant saddle cannot contribute to this amplitude, because a path staying near $q_-$ never ends at $q_+$. The leading contribution is the one-instanton saddle.

Expanding around the instanton,

$$
q(\tau)=q_I(\tau)+\eta(\tau),
$$

gives

$$
S_E[q]
=
\frac{A}{g}
+
\frac{1}{2g}\int d\tau\,\eta(\tau)\mathcal M\eta(\tau)
+
\cdots,
$$

with fluctuation operator

$$
\mathcal M
=
-\frac{d^2}{d\tau^2}+U''(q_I(\tau)).
$$

Because $q_I(\tau-\tau_0)$ is a family of solutions, the derivative

$$
\eta_0(\tau)=\dot q_I(\tau)
$$

is a zero mode:

$$
\mathcal M\eta_0=0.
$$

The determinant of $\mathcal M$ is therefore not taken over all modes. The zero eigenvalue is removed and replaced by an integral over the collective coordinate $\tau_0$.

The one-instanton contribution has the schematic form

$$
K_{+-}^{(1)}(T)
\simeq
T\,\kappa\,e^{-A/g}\,K_{\rm osc}(T),
$$

where $K_{\rm osc}(T)$ is the harmonic-oscillator contribution in one well and

$$
\kappa
=
\left(\frac{A}{2\pi g}\right)^{1/2}
\left[
\frac{\det \mathcal M_{\rm vac}}{\det'\mathcal M}
\right]^{1/2}
\times
\left(\text{normalization conventions}\right).
$$

The prime on $\det'$ means that the translational zero mode is excluded. The factor of $T$ comes from integrating the instanton center over the Euclidean interval.

The even and odd parity amplitudes behave at large $T$ as

$$
K_{++}(T)\pm K_{+-}(T)
\sim
e^{-T E_\pm}.
$$

Summing the dilute gas of alternating instantons and anti-instantons gives

$$
E_\pm
=
E_{\rm pert}\mp \kappa e^{-A/g}+O(e^{-2A/g}),
$$

so the leading splitting is

$$
\Delta E=E_- - E_+
=2\kappa e^{-A/g}+O(e^{-2A/g}).
$$

This is the first calculation in which all the familiar ingredients of instanton calculus appear in a fully visible way: a nontrivial Euclidean saddle, a classical action, a fluctuation determinant, a zero-mode Jacobian, and a collective-coordinate integral.

## Why the dilute gas exponentiates

The one-instanton term is not the end. For large $T$, a path can tunnel many times:

$$
q_-\to q_+\to q_-\to q_+\to\cdots.
$$

When the instantons are well separated, the action is approximately additive:

$$
S_E[q_{n\text{-inst}}]\simeq \frac{nA}{g}.
$$

The centers $\tau_1,\ldots,\tau_n$ are ordered along the Euclidean interval. Ignoring interactions for the moment, their integral gives

$$
\int_{-T/2<\tau_1<\cdots<\tau_n<T/2}d\tau_1\cdots d\tau_n
=\frac{T^n}{n!}.
$$

Thus a sum over rare events becomes an exponential:

$$
\sum_{n=0}^\infty \frac1{n!}\left(T\kappa e^{-A/g}\right)^n
=
\exp\left(T\kappa e^{-A/g}\right).
$$

The parity projection determines whether even or odd numbers of tunneling events contribute. In the end, the exponentiation of the dilute gas becomes the energy shift written above.

This is the same combinatorial mechanism that appears in more complicated settings. A gas of rare localized events contributes an exponential to the partition function or an effective potential. What changes in QFT is that each event also has a position in spacetime, internal orientations, size moduli, fermion zero modes, and interactions.

## Periodic potentials and theta-like labels

A periodic potential has infinitely many equivalent minima:

$$
U(q+L)=U(q),
\qquad
q_n=q_0+nL.
$$

Perturbation theory around each $q_n$ gives the same localized ground state. The true eigenstates are Bloch superpositions,

$$
|\theta\rangle
\simeq
\sum_{n\in\mathbb Z}e^{in\theta}|n\rangle,
\qquad
\theta\sim\theta+2\pi.
$$

The Euclidean path integral decomposes into sectors labeled by the winding number $\ell$:

$$
q(T/2)=q(-T/2)+\ell L.
$$

The theta-projected partition function is

$$
Z(\theta,T)
=
\sum_{\ell\in\mathbb Z}e^{i\ell\theta}Z_\ell(T).
$$

At leading order, the $\ell=\pm1$ sectors are dominated by one instanton and one anti-instanton. The ground-state energy becomes

$$
E_0(\theta)
=
E_{\rm pert}-2\kappa e^{-A/g}\cos\theta+O(e^{-2A/g}).
$$

This formula is the one-dimensional ancestor of theta vacua in gauge theory. Later, the integer $\ell$ will be replaced by the Yang–Mills topological charge $Q$, and the factor $e^{i\ell\theta}$ will become $e^{i\theta Q}$.

The periodic-potential example is conceptually priceless: it shows that an angular parameter can label superselection-like sectors of the quantum theory even though the local perturbative expansion near any one minimum looks identical.

## False vacua versus degenerate vacua

Instantons in degenerate minima and bounces in false vacua are close cousins, but they answer different questions.

In a degenerate double well, the instanton connects two minima of equal energy. It contributes to real energy splittings or band widths. The fluctuation operator around the instanton has a zero mode from translation, but no negative mode in the tunneling-splitting problem.

In a metastable potential, the bounce starts and ends at the false vacuum in Euclidean time. It describes decay, not splitting. The fluctuation operator has one negative mode. That negative mode is exactly what produces an imaginary part of the false-vacuum energy and hence a decay rate.

Schematically,

$$
\text{instanton between degenerate minima}
\quad\Rightarrow\quad
\Delta E\sim e^{-A/g},
$$

whereas

$$
\text{bounce from a false vacuum}
\quad\Rightarrow\quad
\Gamma\sim e^{-B/g}.
$$

The same Euclidean technology appears in both cases: saddles, determinants, zero modes, collective coordinates, and dilute sums. The interpretation differs because the boundary conditions and the spectrum of fluctuations differ.

## What perturbation theory misses

Near a single minimum, perturbation theory produces a formal series

$$
E_{\rm pert}(g)=\sum_{n=0}^\infty a_n g^n.
$$

The instanton contribution is not one of the terms in this series:

$$
e^{-A/g}
\notin
\left\{1,g,g^2,\ldots\right\}.
$$

Indeed, for every $N$,

$$
\lim_{g\to0^+}\frac{e^{-A/g}}{g^N}=0.
$$

This is why the instanton is invisible in perturbation theory to all finite orders. Yet it can dominate the splitting between states that are exactly degenerate in perturbation theory.

The sharper modern statement is that physical answers often have transseries structure,

$$
E(g)
\sim
\sum_{n=0}^\infty a_n g^n
+
\sum_{k=1}^\infty e^{-kA/g}
\sum_{n=0}^\infty a_{k,n}g^n
+
\cdots.
$$

The dots may include logarithms, complex saddles, or correlated instanton–anti-instanton sectors. The double-well and periodic potentials are among the best places to learn this structure without being buried under gauge fixing.

## Common pitfalls

**Confusing real-time tunneling with a Euclidean classical trajectory.** The instanton is not the path followed by the particle in real time. It is a saddle of the imaginary-time path integral.

**Dropping the zero mode from the determinant but forgetting to put it back.** The zero mode is not simply discarded. It is replaced by an integral over the instanton center, producing the factor of $T$ and a Jacobian.

**Treating the instanton prefactor as universal.** The exponential $e^{-A/g}$ is robust once the saddle is fixed. The prefactor depends on determinant normalization, boundary conditions, the definition of $g$, and the observable.

**Assuming multi-instantons are always exact solutions.** In the one-dimensional double well, separated multi-instanton configurations are approximate saddles. In Yang–Mills theory, multi-instanton moduli spaces contain exact solutions. Same vocabulary; different geometry.

**Forgetting the anti-instanton.** If an instanton increases the winding number, an anti-instanton decreases it. Real quantities often involve both, for example through $\cos\theta$.

**Calling every Euclidean saddle an instanton.** In careful usage, bounces, real instantons, complex instantons, and renormalon-like effects are distinct. They may live in the same semiclassical zoo, but they are not identical animals.

## Relations to other pages

This page is the entry point to [Instantons, Tunneling, and Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/). The next page, [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), explains what changes when the single coordinate $q(\tau)$ is replaced by fields $\Phi(x)$.

The determinant and collective-coordinate pieces reuse [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/) and [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/). The many-event sum is the prototype for [Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/) and [Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/). The distinction between instantons and bounces is developed in [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/).

The periodic-potential sector sum is the small model for [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), where the label $\theta$ becomes the Yang–Mills theta angle. The asymptotic and transseries viewpoint connects forward to the later Resurgence and Transseries chapter.

## Research status

The leading instanton calculation in one-dimensional quantum mechanics is established textbook material. The double-well and periodic-potential formulas can be checked by WKB, path integrals, exact quantization conditions, and high-precision numerical diagonalization.

The active research value of these examples is that they are solvable enough to expose deeper structures: large-order perturbation theory, Borel summability, non-Borel summability, instanton–anti-instanton ambiguities, exact WKB, resurgence, and the role of complex saddles. So this is not just a warmup. It is a tiny model of several genuinely modern issues, with most of the irrelevant complications stripped away.

## Exercises

### Exercise 1: first integral for a Euclidean instanton

Let

$$
S_E[q]=\frac1g\int d\tau\left[\frac12\dot q^2+U(q)\right],
$$

where $U(q_\pm)=0$. Show that any finite-action solution interpolating from $q_-$ to $q_+$ obeys

$$
\frac12\dot q^2=U(q).
$$

<details><summary><strong>Solution</strong></summary>

The Euclidean equation of motion is

$$
\ddot q=U'(q).
$$

Multiply by $\dot q$:

$$
\dot q\ddot q=U'(q)\dot q.
$$

This is

$$
\frac{d}{d\tau}\left(\frac12\dot q^2-U(q)\right)=0.
$$

Therefore

$$
\frac12\dot q^2-U(q)=C.
$$

Finite action requires $q\to q_\pm$ and $\dot q\to0$ at $\tau\to\pm\infty$. Since $U(q_\pm)=0$, the constant is $C=0$. Hence

$$
\frac12\dot q^2=U(q).
$$

</details>

### Exercise 2: instanton action in the dimensionless double well

For

$$
U(q)=\frac12(q^2-1)^2,
$$

show that the instanton action without the overall $1/g$ factor is

$$
A=\frac43.
$$

<details><summary><strong>Solution</strong></summary>

Using the first-integral formula,

$$
A=\int_{-1}^{1}dq\,\sqrt{2U(q)}.
$$

For $-1\le q\le 1$,

$$
\sqrt{2U(q)}=\sqrt{(q^2-1)^2}=1-q^2.
$$

Therefore

$$
A=\int_{-1}^{1}(1-q^2)dq
=\left[q-\frac{q^3}{3}\right]_{-1}^{1}
=\frac43.
$$

</details>

### Exercise 3: why the instanton derivative is a zero mode

Let $q_I(\tau-\tau_0)$ be a one-parameter family of instanton solutions. Show that

$$
\eta_0(\tau)=\dot q_I(\tau)
$$

is a zero mode of

$$
\mathcal M=-\frac{d^2}{d\tau^2}+U''(q_I(\tau)).
$$

<details><summary><strong>Solution</strong></summary>

The instanton equation is

$$
\ddot q_I=U'(q_I).
$$

Differentiate with respect to $\tau$:

$$
\dddot q_I=U''(q_I)\dot q_I.
$$

Rearranging gives

$$
\left(-\frac{d^2}{d\tau^2}+U''(q_I)\right)\dot q_I=0.
$$

Thus $\eta_0=\dot q_I$ is a zero mode. Equivalently, it is the infinitesimal change of the solution under translation of its center.

</details>

### Exercise 4: theta dependence in a periodic potential

Assume that the one-instanton and one-anti-instanton sectors in a periodic potential contribute $T\kappa e^{-A/g}$ each, weighted by $e^{i\theta}$ and $e^{-i\theta}$. Show that the leading theta-dependent ground-state energy is

$$
E_0(\theta)=E_{\rm pert}-2\kappa e^{-A/g}\cos\theta+\text{higher instantons}.
$$

<details><summary><strong>Solution</strong></summary>

At large $T$,

$$
Z(\theta,T)\sim e^{-T E_0(\theta)}.
$$

Keeping only the vacuum, one-instanton, and one-anti-instanton sectors gives

$$
Z(\theta,T)
\simeq
 e^{-T E_{\rm pert}}
\left(1+T\kappa e^{-A/g}e^{i\theta}+T\kappa e^{-A/g}e^{-i\theta}+\cdots\right).
$$

The two one-event terms combine to

$$
2T\kappa e^{-A/g}\cos\theta.
$$

Exponentiating to leading order in the dilute gas,

$$
Z(\theta,T)
\simeq
\exp\left[-T E_{\rm pert}+2T\kappa e^{-A/g}\cos\theta\right].
$$

Thus

$$
E_0(\theta)=E_{\rm pert}-2\kappa e^{-A/g}\cos\theta+\cdots.
$$

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the instanton and false-vacuum lectures.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on instantons in quantum mechanics, degenerate minima, multi-instantons, and large-order behavior.
- M. Mariño, *Instantons and Large N*, chapter 1, for a detailed and modern path-integral treatment of instantons in quantum mechanics.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter 5, for the bridge from quantum-mechanical tunneling to Yang–Mills instantons.
- C. G. Callan and S. Coleman, “Fate of the False Vacuum. II. First Quantum Corrections,” for the classic determinant treatment in the decay problem.

## Version history

- **2026-06-27:** Initial polished page. Added the double-well derivation, determinant structure, dilute-gas exponentiation, periodic-potential theta analogy, and exercises.
- **2026-06-27:** Linked the periodic-potential analogy forward to Theta Vacua after drafting that page.
- **2026-06-27:** Linked the multi-instanton discussion to Instanton Gas after drafting that page.
