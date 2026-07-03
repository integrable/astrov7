---
title: "Quantum-Mechanical Path Integral"
description: "The time-sliced derivation of the path integral in ordinary quantum mechanics, its phase-space and Lagrangian forms, source insertions, Euclidean continuation, and the bridge to field-theory functional integrals."
sidebar:
  label: "Quantum-Mechanical Path Integral"
  order: 2
---

## Summary

The quantum-mechanical path integral rewrites a transition amplitude as a sum over histories. For a particle moving in one dimension with Lagrangian

$$
L(q,\dot q)=\frac12m\dot q^2-V(q),
$$

the transition amplitude from $q_i$ at time $t_i$ to $q_f$ at time $t_f$ is formally

$$
\boxed{
K(q_f,t_f;q_i,t_i)
=\langle q_f|e^{-iH(t_f-t_i)}|q_i\rangle
=\int_{q(t_i)=q_i}^{q(t_f)=q_f}\mathcal Dq\,e^{iS[q]},
}
$$

where

$$
S[q]=\int_{t_i}^{t_f}dt\,L(q,\dot q).
$$

This formula is not a slogan about a particle literally choosing every possible route. It is a compact representation of ordinary unitary quantum mechanics. It follows from slicing the time-evolution operator into many short intervals, inserting complete sets of position states, and taking a continuum limit. Dirac anticipated the action-based viewpoint, Feynman developed the path-integral formulation in quantum mechanics, and Weinberg derives the field-theory path-integral rules from the canonical formalism precisely to preserve the connection with unitarity (Dirac 1933; Feynman 1948; Weinberg 1995, Vol. I, §9.1).

The most important lesson for QFT is structural:

```txt
quantum mechanics: integrate over paths q(t)
field theory:       integrate over field histories φ(x,t)
```

A scalar field path integral is not a sum over particle paths. It is the infinite-dimensional analogue of the ordinary path integral, with the coordinate $q(t)$ replaced by a field value at every point of space.

## Prerequisites

You should know [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/), [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/), and [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/).

## Core idea

The path integral comes from three ordinary facts:

```txt
1. Time evolution composes.
2. Position states form a complete basis.
3. Short-time propagation is controlled by the classical action.
```

<figure class="doc-figure" style="--figure-width: 46rem;">

![Time slicing and summing over paths in the quantum-mechanical path integral](/figures/foundations/qm-time-slicing-paths.svg)

<figcaption>

Time slicing turns a transition amplitude into an integral over intermediate positions. In the continuum limit, a sequence of intermediate points becomes a path $q(t)$, and each path is weighted by $e^{iS[q]}$ in Lorentzian signature.

</figcaption>
</figure>

For a finite number of time slices, there is no mystery: we are just multiplying kernels and integrating over intermediate positions. The formal object $\int\mathcal Dq$ is the shorthand that remains after the number of slices goes to infinity.

## Time slicing the kernel

Let

$$
T=t_f-t_i,
\qquad
\Delta t=\frac{T}{N},
\qquad
t_n=t_i+n\Delta t.
$$

The transition kernel is

$$
K(q_f,t_f;q_i,t_i)
=\langle q_f|e^{-iHT}|q_i\rangle.
$$

Split the time-evolution operator into $N$ factors:

$$
e^{-iHT}=\left(e^{-iH\Delta t}\right)^N.
$$

Insert the identity

$$
1=\int_{-\infty}^{\infty}dq_n\,|q_n\rangle\langle q_n|
$$

between adjacent factors. With $q_0=q_i$ and $q_N=q_f$,

$$
K(q_f,t_f;q_i,t_i)
=\int\prod_{n=1}^{N-1}dq_n
\prod_{n=0}^{N-1}
\langle q_{n+1}|e^{-iH\Delta t}|q_n\rangle.
$$

This equation is exact for any finite $N$. All the physics is now in the short-time kernel.

For the Hamiltonian

$$
H=\frac{p^2}{2m}+V(q),
$$

the leading small-$\Delta t$ kernel is

$$
\langle q_{n+1}|e^{-iH\Delta t}|q_n\rangle
\simeq
\left(\frac{m}{2\pi i\Delta t}\right)^{1/2}
\exp\left\{i\Delta t\left[
\frac{m}{2}\left(\frac{q_{n+1}-q_n}{\Delta t}\right)^2
-V(q_n)
\right]\right\}.
$$

Multiplying the short-time kernels gives

$$
K(q_f,t_f;q_i,t_i)
=\lim_{N\to\infty}
\left(\frac{m}{2\pi i\Delta t}\right)^{N/2}
\int\prod_{n=1}^{N-1}dq_n\,
\exp\left\{i\sum_{n=0}^{N-1}\Delta t\left[
\frac{m}{2}\left(\frac{q_{n+1}-q_n}{\Delta t}\right)^2
-V(q_n)
\right]\right\}.
$$

In the continuum limit,

$$
\sum_n\Delta t\,L\left(q_n,\frac{q_{n+1}-q_n}{\Delta t}\right)
\longrightarrow
\int_{t_i}^{t_f}dt\,L(q,\dot q),
$$

and the product of ordinary integrals becomes the formal measure $\mathcal Dq$.

:::note[Discretization convention]
The expression above evaluates the potential at $q_n$. Other choices, such as midpoint evaluation, differ by terms that vanish for simple Hamiltonians in the continuum limit. For more complicated systems, especially with coordinate-dependent kinetic terms or constraints, the discretization can affect operator ordering and measure factors. Weinberg stresses this point in deriving path integrals from canonical quantum mechanics (Weinberg 1995, Vol. I, §§9.1–9.3).
:::

## Phase-space form

The Lagrangian path integral is not the most primitive version. The canonical derivation naturally gives the phase-space path integral

$$
\boxed{
K(q_f,t_f;q_i,t_i)
=\int\mathcal Dp\,\mathcal Dq\,
\exp\left\{i\int_{t_i}^{t_f}dt\,[p\dot q-H(p,q)]\right\},
}
$$

with the boundary conditions on $q(t)$, not on $p(t)$.

For

$$
H(p,q)=\frac{p^2}{2m}+V(q),
$$

the momentum integral is Gaussian:

$$
p\dot q-\frac{p^2}{2m}-V(q)
=-\frac{1}{2m}(p-m\dot q)^2+\frac12m\dot q^2-V(q).
$$

Integrating over $p$ gives a normalization factor times

$$
\exp\left\{i\int dt\left[\frac12m\dot q^2-V(q)\right]\right\}.
$$

That is the Lagrangian path integral. The move from phase space to configuration space is therefore a Gaussian integration, not a new principle.

## What the measure means

The symbol

$$
\int\mathcal Dq
$$

means a regulated limit. In the time-sliced definition above,

$$
\mathcal Dq
\sim
\lim_{N\to\infty}
\left(\frac{m}{2\pi i\Delta t}\right)^{N/2}
\prod_{n=1}^{N-1}dq_n.
$$

The proportionality sign is deliberate. Overall normalization depends on the precise endpoint convention, boundary condition, and whether one computes a transition kernel, a vacuum functional, or a normalized expectation value. For most QFT applications, source-independent constants cancel from normalized correlators and are absorbed into $\mathcal N$.

The important invariant content is not the bare symbol $\mathcal Dq$ but the regulated rule:

```txt
approximate the history by finitely many variables,
perform ordinary integrals,
then take a controlled limit.
```

That is why lattice regularization, heat-kernel regularization, zeta regularization, Pauli–Villars fields, and dimensional regularization are not cosmetic. They are ways of saying what infinite-dimensional expressions mean.

## Stationary phase and the classical limit

The classical path is not the only path in the path integral. But when the action is large in units of $\hbar$, phases oscillate rapidly and cancel except near stationary points of $S$.

Restoring $\hbar$ for one line,

$$
K\sim\int\mathcal Dq\,e^{iS[q]/\hbar}.
$$

A small variation gives

$$
S[q+\delta q]=S[q]+\delta S[q]+\cdots.
$$

If $\delta S\ne0$, nearby paths have rapidly varying phases and cancel. The leading contribution comes from

$$
\delta S=0,
$$

which gives the Euler–Lagrange equation. The next correction is the Gaussian integral over fluctuations around the classical path. This is the finite-dimensional saddle-point idea applied to histories.

This is why the path integral makes the classical limit visually obvious:

```txt
classical mechanics: stationary action
quantum mechanics:  all histories weighted by phase, dominated semiclassically by stationary action
```

## Time-ordered insertions

Path integrals naturally compute time-ordered products. In the phase-space derivation, insertions of operators at intermediate times appear in the order in which the time-evolution factors are multiplied. If the times are arbitrary, the result is the matrix element of the corresponding time-ordered product (Weinberg 1995, Vol. I, §9.1).

For example, with boundary states suppressed schematically,

$$
\langle T\{q(t_1)q(t_2)\}\rangle
=\frac{\int\mathcal Dq\,q(t_1)q(t_2)e^{iS[q]}}
{\int\mathcal Dq\,e^{iS[q]}}.
$$

This is the first major bridge to QFT. The path integral does not primarily produce unordered correlators; it produces the time-ordered objects used in perturbation theory and Feynman rules.

For a source $j(t)$ coupled to $q(t)$, define

$$
Z[j]
=\left\langle0\left|T\exp\left(i\int dt\,j(t)q(t)\right)\right|0\right\rangle.
$$

Then

$$
\boxed{
\langle0|T\{q(t_1)\cdots q(t_n)\}|0\rangle
=\left.\frac{1}{i^n}\frac{\delta^n Z[j]}
{\delta j(t_1)\cdots\delta j(t_n)}\right|_{j=0}.
}
$$

This is the one-dimensional ancestor of the field-theory formula

$$
\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle
=\left.\frac{1}{i^n}\frac{\delta^n Z[J]}
{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
$$

## Harmonic oscillator check

The harmonic oscillator is the canonical Gaussian path integral. For

$$
L=\frac12m\dot q^2-\frac12m\omega^2q^2,
$$

the vacuum source functional is

$$
\boxed{
Z_0[j]
=\exp\left[-\frac12\int dt\,dt'\,j(t)D_F(t-t')j(t')\right],
}
$$

where

$$
\boxed{
D_F(t-t')=\langle0|T\{q(t)q(t')\}|0\rangle
=\frac{1}{2m\omega}e^{-i\omega|t-t'|}.
}
$$

This is exactly the Gaussian story from [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/), with the finite matrix replaced by the differential operator

$$
m\left(\frac{d^2}{dt^2}+\omega^2\right)
$$

plus the Feynman boundary prescription. The inverse of that operator, with the correct prescription, is the oscillator propagator.

The scalar field is obtained by replacing the single oscillator with infinitely many oscillator modes, one for each momentum.

## Euclidean continuation

The Lorentzian path integral is oscillatory:

$$
e^{iS[q]}.
$$

It is not a convergent probability measure. For many purposes one rotates to imaginary time,

$$
t=-i\tau,
$$

and obtains the Euclidean weight

$$
e^{-S_E[q]}.
$$

For the particle,

$$
S_E[q]=\int d\tau\left[\frac12m\left(\frac{dq}{d\tau}\right)^2+V(q)\right]
$$

when $V$ is bounded below. This looks like a Boltzmann weight. Polyakov emphasizes the same analogy: quantum mechanics in $d$ dimensions is closely related to classical statistical mechanics in $d+1$ Euclidean dimensions (Polyakov 1987, ch. 1).

The Euclidean version is often the mathematically cleaner object. The Lorentzian theory is recovered by analytic continuation when the required analyticity and positivity conditions hold. This becomes a serious topic in [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) and [Reflection Positivity](/foundations/structural-principles/reflection-positivity/).

## Why this matters for QFT

The path integral does three foundational jobs in QFT.

First, it makes Lorentz covariance manifest. The operator formalism makes Hilbert space and unitarity transparent, but covariance can be hidden by equal-time choices. The path integral begins with the action $S=\int d^4x\,\mathcal L$, which is often manifestly Lorentz invariant.

Second, it packages perturbation theory. Expanding

$$
e^{iS_{\mathrm{int}}}
$$

inside a Gaussian integral generates Wick contractions and Feynman diagrams automatically. This is the path-integral version of the Wick expansion.

Third, it exposes saddle points and topology. Instantons, solitons, tunneling, anomalies, and semiclassical expansions are much easier to formulate as statements about fields in an action functional than as direct operator manipulations.

But there is a tradeoff. The operator formalism makes unitarity visible; the Lorentzian path integral makes covariance visible. Weinberg puts the point sharply: path integrals give manifestly Lorentz-invariant diagrammatic rules, but unitarity is most directly justified by deriving them from the canonical formalism (Weinberg 1995, Vol. I, ch. 9).

## Common pitfalls

### The path integral is not automatically rigorous

The finite-dimensional Gaussian is a theorem. The formal continuum path integral is a definition scheme that needs regularization. A trustworthy calculation says which regulated object is being used or why the formal manipulations are safe.

### The classical path is not the only path

The stationary path dominates in a semiclassical approximation. The exact path integral includes fluctuations. Saying “the particle takes all paths” is a metaphor; the controlled statement is a time-sliced integral representation of a quantum amplitude.

### The measure is not always trivial

For simple Cartesian coordinates, the measure is essentially the product of $dq_n$. In curvilinear coordinates, constrained systems, gauge theories, and nonlinear sigma models, the measure can contain determinants and Jacobians. Some of the most interesting physics hides there.

### Euclidean time is not just a typo in time

The continuation $t=-i\tau$ changes oscillatory weights into decaying weights and changes the meaning of boundary conditions. It is powerful precisely because it is not a harmless relabeling.

### The field path integral is not a particle path integral

In QFT, $\phi(x)$ is integrated as a field configuration over spacetime. Feynman diagrams may look like particle paths, but they are bookkeeping devices for field correlators, not literal worldline histories in the basic scalar-field path integral.

## Relation to other topics

- [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/) supplies the algebraic identity behind Gaussian path integrals.
- [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) replaces $q(t)$ by $\phi(t,\mathbf x)$.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) develops the source calculus systematically.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) explains Wick rotation and the statistical-mechanics form of the path integral.
- [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/) expands around nontrivial saddles.
- [Constraints](/foundations/classical-field-theory/constraints/) and [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) explain why gauge theories need more than the naive measure.

## Research status

- **Established:** The time-sliced path integral for ordinary quantum mechanics and its equivalence to the canonical formalism are standard.
- **Subtle:** Infinite-dimensional measures, real-time convergence, operator-ordering issues, constraints, and gauge fixing require care.
- **Bridge:** This page is a bridge from ordinary quantum mechanics to functional integrals in QFT, not a full mathematical construction of the continuum measure.

## Exercises

### Exercise 1: Free-particle short-time kernel

Starting from

$$
H=\frac{p^2}{2m},
$$

show that

$$
\langle q'|e^{-iH\Delta t}|q\rangle
=\left(\frac{m}{2\pi i\Delta t}\right)^{1/2}
\exp\left[\frac{im(q'-q)^2}{2\Delta t}\right]
$$

for $\Delta t>0$.

<details>
<summary><strong>Solution</strong></summary>

Insert momentum states with

$$
\langle q|p\rangle=e^{ipq},
\qquad
1=\int\frac{dp}{2\pi}|p\rangle\langle p|.
$$

Then

$$
\langle q'|e^{-ip^2\Delta t/(2m)}|q\rangle
=\int\frac{dp}{2\pi}\,
\exp\left[-i\frac{p^2}{2m}\Delta t+ip(q'-q)\right].
$$

Complete the square in $p$:

$$
-i\frac{\Delta t}{2m}p^2+ip(q'-q)
=-i\frac{\Delta t}{2m}\left(p-\frac{m(q'-q)}{\Delta t}\right)^2
+\frac{im(q'-q)^2}{2\Delta t}.
$$

The remaining Gaussian gives

$$
\int\frac{dp}{2\pi}\,e^{-i\Delta t p^2/(2m)}
=\left(\frac{m}{2\pi i\Delta t}\right)^{1/2}.
$$

Therefore

$$
\langle q'|e^{-iH\Delta t}|q\rangle
=\left(\frac{m}{2\pi i\Delta t}\right)^{1/2}
\exp\left[\frac{im(q'-q)^2}{2\Delta t}\right].
$$

</details>

### Exercise 2: Momentum integration gives the Lagrangian

Use the phase-space exponent

$$
\int dt\left[p\dot q-\frac{p^2}{2m}-V(q)\right]
$$

to show that integrating over $p$ gives the Lagrangian action up to a normalization factor.

<details>
<summary><strong>Solution</strong></summary>

Complete the square:

$$
p\dot q-\frac{p^2}{2m}-V(q)
=-\frac{1}{2m}(p-m\dot q)^2+\frac12m\dot q^2-V(q).
$$

The $p$-dependent term is Gaussian and contributes a factor independent of $q$ for this simple system. The remaining exponent is

$$
i\int dt\left[\frac12m\dot q^2-V(q)\right]
=iS[q].
$$

Thus the configuration-space path integral has the Lagrangian

$$
L=\frac12m\dot q^2-V(q).
$$

</details>

### Exercise 3: Stationary phase and Newton's equation

For

$$
S[q]=\int_{t_i}^{t_f}dt\left[\frac12m\dot q^2-V(q)\right],
$$

with fixed endpoints, show that $\delta S=0$ gives

$$
m\ddot q=-V'(q).
$$

<details>
<summary><strong>Solution</strong></summary>

Vary $q\to q+\delta q$ with $\delta q(t_i)=\delta q(t_f)=0$. Then

$$
\delta S=\int dt\left[m\dot q\,\delta\dot q-V'(q)\delta q\right].
$$

Integrate the first term by parts:

$$
\int dt\,m\dot q\,\delta\dot q
=\left[m\dot q\,\delta q\right]_{t_i}^{t_f}
-\int dt\,m\ddot q\,\delta q.
$$

The boundary term vanishes. Hence

$$
\delta S=-\int dt\,[m\ddot q+V'(q)]\delta q.
$$

Since $\delta q$ is arbitrary in the interior,

$$
m\ddot q=-V'(q).
$$

</details>

### Exercise 4: Oscillator propagator as a Green function

For the harmonic oscillator, verify that

$$
D_F(t)=\frac{1}{2m\omega}e^{-i\omega|t|}
$$

satisfies

$$
m\left(\frac{d^2}{dt^2}+\omega^2\right)D_F(t)=-i\delta(t).
$$

<details>
<summary><strong>Solution</strong></summary>

For $t\ne0$,

$$
\left(\frac{d^2}{dt^2}+\omega^2\right)e^{-i\omega|t|}=0.
$$

The delta function comes from differentiating $|t|$. Compute the jump in the first derivative:

$$
D_F'(0^+)=\frac{1}{2m\omega}(-i\omega)=-\frac{i}{2m},
$$

while

$$
D_F'(0^-)=\frac{1}{2m\omega}(+i\omega)=\frac{i}{2m}.
$$

Thus

$$
D_F'(0^+)-D_F'(0^-)=-\frac{i}{m}.
$$

Therefore the second derivative contains

$$
-\frac{i}{m}\delta(t),
$$

and

$$
m\left(\frac{d^2}{dt^2}+\omega^2\right)D_F(t)=-i\delta(t).
$$

</details>

### Exercise 5: Euclidean particle action

Starting with

$$
S[q]=\int dt\left[\frac12m\dot q^2-V(q)\right],
$$

set $t=-i\tau$ and show that $iS=-S_E$, with

$$
S_E[q]=\int d\tau\left[\frac12m\left(\frac{dq}{d\tau}\right)^2+V(q)\right].
$$

<details>
<summary><strong>Solution</strong></summary>

With $t=-i\tau$,

$$
dt=-i\,d\tau,
\qquad
\frac{dq}{dt}=\frac{dq/d\tau}{dt/d\tau}=i\frac{dq}{d\tau}.
$$

Therefore

$$
\frac12m\dot q^2-V(q)
=\frac12m\left(i\frac{dq}{d\tau}\right)^2-V(q)
=-\frac12m\left(\frac{dq}{d\tau}\right)^2-V(q).
$$

Thus

$$
S=(-i)\int d\tau\left[-\frac12m\left(\frac{dq}{d\tau}\right)^2-V(q)\right]
=i\int d\tau\left[\frac12m\left(\frac{dq}{d\tau}\right)^2+V(q)\right].
$$

So

$$
iS=-S_E.
$$

</details>

### Exercise 6: Why time ordering appears

Explain why the path integral with insertions $q(t_1)q(t_2)$ computes a time-ordered correlator, not an ordinary product with a fixed written order.

<details>
<summary><strong>Solution</strong></summary>

In the time-sliced derivation, factors of the evolution operator are multiplied in chronological order. An insertion at a later time appears closer to the left bra state than an insertion at an earlier time. Therefore, when one reconstructs the operator expression, later operators stand to the left of earlier operators.

If $t_1>t_2$, the insertion corresponds to

$$
\langle\cdots q(t_1)q(t_2)\cdots\rangle.
$$

If $t_2>t_1$, the same c-number product inside the path integral corresponds to

$$
\langle\cdots q(t_2)q(t_1)\cdots\rangle.
$$

Thus the path integral computes

$$
\langle T\{q(t_1)q(t_2)\}\rangle.
$$

</details>

## Sources and further reading

### Primary references

- P. A. M. Dirac, “The Lagrangian in Quantum Mechanics,” *Physikalische Zeitschrift der Sowjetunion* **3** (1933), for the early observation that the action controls short-time quantum propagation.
- R. P. Feynman, “Space-Time Approach to Non-Relativistic Quantum Mechanics,” *Reviews of Modern Physics* **20** (1948), for the path-integral formulation of quantum mechanics.
- R. P. Feynman and A. R. Hibbs, *Quantum Mechanics and Path Integrals*, for the classic systematic treatment.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, §§6–7, for the quantum-mechanical and harmonic-oscillator path integrals.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.2, for the intuitive “sum over paths” motivation.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 28, for the transition from functional integration to Feynman rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§9.1–9.3, for a canonical derivation of the phase-space and Lagrangian path integrals.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §9.1, for the transition from quantum-mechanical path integrals to field theory.

### For a first pass

- Zee, ch. I.2.
- Srednicki, §§6–7.
- Feynman and Hibbs, early chapters.

### For mathematical precision

- B. Simon, *Functional Integration and Quantum Physics*, for a careful mathematical treatment of functional integration.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for Euclidean functional integrals and constructive QFT.
- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's Functions,” for the Euclidean reconstruction viewpoint.

## Version history

- **2026-05-23:** Initial qft.org page on the quantum-mechanical path integral, time slicing, phase-space form, source insertions, oscillator Gaussian, Euclidean continuation, and the bridge to scalar-field functional integrals.
