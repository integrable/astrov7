---
title: "Correlation Length"
description: "Defines correlation length as a long-distance diagnostic of phases, derives its relation to exponential decay and critical scaling, and explains its channel dependence in QFT."
sidebar:
  label: "Correlation Length"
  order: 3
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut; Zinn-Justin; Di Francesco–Mathieu–Sénéchal; Fradkin; Srednicki."
topics:
  - correlation length
  - connected correlators
  - exponential clustering
  - critical scaling
  - finite-size scaling
  - mass scale
canonicalTopics:
  - nonperturbative-qft
  - correlation-functions
  - phase-diagnostics
  - critical-phenomena
  - mass-gap
researchStatus:
  established:
    - "Correlation lengths extracted from connected correlators and transfer matrices are standard diagnostics of massive phases, critical points, and continuum limits."
  active:
    - "In gauge theories, real-time systems, finite-temperature systems, and topological phases, the physically relevant correlation length can be channel-dependent and may not coincide with a unique particle mass."
---

## Summary

A **correlation length** is the distance scale over which connected correlations decay. If $\mathcal O$ is a local operator and the state is translation invariant, define

$$
G_{\mathcal O,c}(x)
=\langle \mathcal O(x)\mathcal O(0)\rangle
-\langle \mathcal O\rangle^2.
$$

In a massive Euclidean theory, many connected correlators have long-distance behavior of the form

$$
G_{\mathcal O,c}(r)
\sim A_{\mathcal O}\frac{e^{-r/\xi_{\mathcal O}}}{r^p},
\qquad r=|x|\to\infty.
$$

The number $\xi_{\mathcal O}$ is the correlation length in the channel probed by $\mathcal O$. In a relativistic zero-temperature QFT, the inverse correlation length is usually the lightest mass that couples to the operator,

$$
\xi_{\mathcal O}^{-1}=m_{\mathcal O},
$$

up to conventions for velocity and units. Near a continuous critical point, the longest correlation length diverges,

$$
\xi\sim |t|^{-\nu},
$$

where $t$ is the relevant tuning parameter and $\nu$ is a critical exponent.

Correlation length is one of the best nonperturbative diagnostics because it is directly visible in Euclidean correlation functions, transfer-matrix spectra, finite-size scaling, and continuum limits. It is also one of the easiest ideas to misuse. There is rarely “the” correlation length without specifying the operator, channel, state, boundary conditions, and limiting procedure.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Schematic extraction of a correlation length from the slope of the logarithm of a connected correlator.](/figures/nonperturbative-qft/correlation-length-exponential-decay.svg)

<figcaption>

For an exponentially decaying connected correlator, $-\log |G_c(r)|$ becomes asymptotically linear in $r$. The inverse slope gives the correlation length. As a critical point is approached, the slope decreases and the longest correlation length grows.

</figcaption>
</figure>

## Prerequisites

You should know [Local Order Parameters](/nonperturbative-qft/order-parameters-diagnostics/local-order-parameters/), [Disorder Parameters](/nonperturbative-qft/order-parameters-diagnostics/disorder-parameters/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), and [Quantum Phase Transitions](/nonperturbative-qft/vacuum-structure-phases/quantum-phase-transitions/).

It also helps to know the Euclidean path integral, connected correlation functions, the idea of a transfer matrix, and the basic statement that continuum QFT near a critical point is controlled by long-distance modes rather than microscopic lattice spacing.

## Core idea

A phase is not only described by which expectation values are nonzero. It is also described by how disturbances fade.

Insert an operator at the origin. Then ask what remains visible far away. If the theory is massive and the operator couples to a massive state, the answer dies exponentially:

$$
G_c(r)\sim e^{-r/\xi}.
$$

If the theory is critical, there is no intrinsic length scale, and connected correlators decay by powers:

$$
G_c(r)\sim \frac{1}{r^{2\Delta_{\mathcal O}}}
$$

for a scaling operator $\mathcal O$, up to anomalous dimensions and normalization conventions. If there is long-range order, the full two-point function may approach a nonzero constant,

$$
\lim_{r\to\infty}\langle \mathcal O(r)\mathcal O(0)\rangle
=\langle\mathcal O\rangle^2,
$$

while the connected part still measures fluctuations around the ordered background.

Thus a correlation length is not an abstract curve-fitting parameter. It is a physical answer to the question:

$$
\text{over what distance does this channel remember a local disturbance?}
$$

The longest correlation length in the theory controls the slowest approach to the infrared. At a continuous transition, this length becomes much larger than the cutoff. That is precisely why universal continuum physics emerges.

## Setup and conventions

We work in Euclidean signature unless explicitly stated otherwise. Let $d$ denote Euclidean spacetime dimension, and let $r=|x|$. For a scalar operator $\mathcal O$, define the connected correlator

$$
G_{\mathcal O,c}(x)
=\langle \mathcal O(x)\mathcal O(0)\rangle
-\langle \mathcal O\rangle^2.
$$

In a translation- and rotation-invariant state, this depends only on $r$. If the operator has spin or internal indices, one first projects onto a definite channel. The correlation length is then the inverse of the smallest exponential decay rate appearing in that channel:

$$
\xi_{\mathcal O}^{-1}
=\text{smallest decay rate visible in }G_{\mathcal O,c}(r).
$$

This definition hides several important words: **visible in that channel**. If $\mathcal O$ has zero matrix element to the lightest state of the theory, its correlator will not see that state. It will see the lightest state with the same quantum numbers and nonzero overlap.

On a lattice with spacing $a$, distances are measured in lattice units unless converted:

$$
r=an,
\qquad
\xi_{\text{physical}}=a\,\xi_{\text{lattice}}.
$$

A continuum limit with a finite physical mass requires

$$
\xi_{\text{lattice}}\to\infty,
\qquad
m_{\text{physical}}=\frac{1}{a\xi_{\text{lattice}}}
\quad\text{fixed}.
$$

This is one of the cleanest reasons criticality matters: the lattice spacing can disappear only when the correlation length in lattice units becomes large.

## Long-distance decay in a massive theory

For a relativistic massive scalar particle of mass $m$, the Euclidean propagator in $d$ dimensions behaves at large $r$ as

$$
\Delta_E(r;m)
\sim C_d\,\frac{m^{(d-3)/2}}{r^{(d-1)/2}}e^{-mr}.
$$

The important part is the exponential. The power of $r$ depends on dimension and on the nature of the lowest spectral threshold; the correlation length is set by the exponential rate.

For a general scalar operator, a spectral representation schematically gives

$$
G_{\mathcal O,c}(r)
=\int_{0}^{\infty}d\mu^2\,\rho_{\mathcal O}(\mu^2)\Delta_E(r;\mu).
$$

If the spectral density has no support below $\mu=m_*$ in this channel, then the leading exponential is

$$
G_{\mathcal O,c}(r)
\sim e^{-m_*r}\times(\text{power of }r),
$$

so

$$
\xi_{\mathcal O}=\frac{1}{m_*}.
$$

If the lightest contribution is a stable one-particle state, $m_*$ is that particle mass. If the lightest contribution is a multiparticle continuum, $m_*$ is the threshold. If the operator does not overlap with either, the correlator sees the next allowed contribution.

This is the real meaning of saying that “mass is inverse correlation length.” It is not a slogan about every length in every system. It is a statement about Euclidean decay in a specified channel.

## Transfer matrix picture

On a Euclidean lattice or in a statistical-mechanical model, the transfer matrix makes the same point without invoking particles. Suppose one direction is called Euclidean time, and let $T$ be the transfer matrix. Its eigenvalues can be written as

$$
\lambda_n=e^{-a_tE_n},
\qquad E_0\le E_1\le E_2\le\cdots.
$$

For an operator $\mathcal O$, the connected time-separated correlator is

$$
C_{\mathcal O}(\tau)
=\langle\mathcal O(\tau)\mathcal O(0)\rangle_c
=\sum_{n>0}|\langle n|\mathcal O|0\rangle|^2e^{-(E_n-E_0)\tau}.
$$

At large $\tau$, the smallest energy difference with nonzero overlap dominates:

$$
C_{\mathcal O}(\tau)
\sim A e^{-\Delta_{\mathcal O}\tau},
\qquad
\Delta_{\mathcal O}=E_{n_*}-E_0.
$$

In an isotropic relativistic continuum limit, Euclidean time and space are related by rotations, so spatial exponential decay and temporal energy decay describe the same mass scale. In anisotropic or nonrelativistic systems, there can be a velocity or dynamical exponent relating them.

## Critical scaling

Near a continuous transition, the longest correlation length diverges. Let $t$ be a relevant tuning parameter measuring distance from criticality, such as

$$
t=\frac{T-T_c}{T_c}
$$

in a thermal transition, or $t=g-g_c$ in a quantum transition. If the relevant coupling has RG eigenvalue $y_t>0$, then under a rescaling by $b$,

$$
t\mapsto b^{y_t}t,
\qquad
\xi(t)\mapsto b^{-1}\xi(b^{y_t}t),
$$

or equivalently

$$
\xi(t)=b\,\xi(b^{y_t}t)
$$

when measuring the original physical length. Choose $b=|t|^{-1/y_t}$ to obtain

$$
\xi(t)\sim |t|^{-1/y_t}.
$$

Thus

$$
\nu=\frac{1}{y_t}.
$$

The exponent $\nu$ is universal within a universality class, while the overall normalization of $\xi$ is not. This distinction is crucial: a numerical value of a correlation length depends on microscopic units, but its divergence exponent is universal.

At the critical point itself, $\xi=\infty$ and connected correlators have scale-invariant behavior. For a scalar primary operator in a CFT,

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
\sim \frac{1}{r^{2\Delta_{\mathcal O}}}.
$$

Away from criticality, the exponential reappears and cuts off the power law at distances $r\gg\xi$.

## Quantum critical points and the dynamical exponent

For a quantum critical point, space and time need not scale the same way. If spatial length scales as

$$
x\mapsto b x,
$$

then time may scale as

$$
t\mapsto b^z t,
$$

where $z$ is the dynamical critical exponent. The spatial correlation length and correlation time behave as

$$
\xi\sim |g-g_c|^{-\nu},
\qquad
\xi_\tau\sim \xi^z.
$$

The gap in the critical channel scales as

$$
\Delta\sim \xi_\tau^{-1}\sim \xi^{-z}.
$$

For a Lorentz-invariant QFT, $z=1$ after choosing units with the effective light velocity equal to one, and the relation reduces to

$$
\Delta\sim \xi^{-1}.
$$

For condensed-matter systems, lattice Hamiltonians, and finite-density systems, $z$ can differ from one. Then the spatial correlation length and the energy gap are still related, but not by the naive relativistic formula.

## Second-moment correlation length

In simulations and data analysis, the asymptotic exponential tail can be noisy. A common alternative is the **second-moment correlation length**. For a sufficiently nice positive rotationally invariant connected correlator in $d$ Euclidean dimensions, define

$$
\xi_{2\text{nd}}^2
=\frac{1}{2d}
\frac{\int d^d x\,x^2G_c(x)}{\int d^d x\,G_c(x)}.
$$

On a lattice, replace integrals by sums. In momentum space, if

$$
\widetilde G(p)=\int d^d x\,e^{-ip\cdot x}G_c(x),
$$

then formally

$$
\xi_{2\text{nd}}^2
=-\frac{1}{2d\,\widetilde G(0)}
\sum_{\mu=1}^{d}
\left.\frac{\partial^2\widetilde G(p)}{\partial p_\mu^2}\right|_{p=0}.
$$

For a single clean pole, the second-moment length agrees with the exponential length up to small corrections. For multiple nearby states, continua, sign-changing correlators, conserved currents, or massless modes, the interpretation requires more care.

The practical lesson is simple: the “correlation length” quoted in a paper or simulation is not fully specified until the estimator is specified.

## Finite-size scaling

A finite box of linear size $L$ cannot support correlations longer than the box. Near a critical point, observables depend on the ratio

$$
\frac{L}{\xi}.
$$

This gives the finite-size scaling form

$$
\mathcal A(t,L)=L^{-\Delta_{\mathcal A}}F_{\mathcal A}(L/\xi)
=L^{-\Delta_{\mathcal A}}F_{\mathcal A}(L^{1/\nu}t),
$$

for an observable with scaling dimension $\Delta_{\mathcal A}$, up to corrections from irrelevant operators and boundary conditions.

In a gapped phase,

$$
L\gg \xi
$$

means finite-size effects are often exponentially small, schematically

$$
\delta\mathcal A(L)\sim e^{-L/\xi}.
$$

At criticality, $\xi$ is effectively replaced by $L$, and finite-size corrections are typically powers of $L$. This is why finite-size scaling is not merely a nuisance. It is a way to measure critical exponents and identify universality classes.

## Ordered, disordered, and critical behavior

A single two-point function can distinguish several broad patterns.

| Behavior of $\langle\mathcal O(r)\mathcal O(0)\rangle$ | Interpretation | Connected correlation length |
|---|---|---|
| Approaches $\langle\mathcal O\rangle^2\neq0$ | Long-range order in a source-selected state. | Fluctuation length extracted from the connected part. |
| Decays as $e^{-r/\xi}$ times a power | Massive channel or finite screening length. | Finite. |
| Decays as a power law | Criticality, Goldstone behavior, Coulomb behavior, or other scale-free sector. | Infinite or not well-defined as a finite exponential length. |
| Decays faster than a chosen operator can detect | Operator has poor overlap with light states. | The extracted length is not the lightest physical length. |
| Oscillates and decays | Ordered wavevector, Fermi momentum, density wave, or complex correlation length. | Envelope gives decay length; oscillation gives momentum scale. |

The table is intentionally cautious. Power-law decay is not automatically a critical point: Goldstone modes, photons, Fermi surfaces, and topological sectors can also produce long-distance structure. Exponential decay is also not automatically confinement: a gapped scalar field has exponential decay but no confined charges.

## Reporting a correlation length

Correlation length is a **channel-dependent infrared diagnostic**, not a property that can be read from a Lagrangian without specifying a probe and a state.

To report it correctly, say:

| Ingredient | Example |
|---|---|
| Operator or probe | $\phi$, $\bar\psi\psi$, a spin operator, a Wilson loop, an energy-density operator. |
| State | Vacuum, thermal state, metastable state, source-selected broken vacuum. |
| Limit | Infinite volume, continuum limit, large separation, zero source, zero temperature. |
| Estimator | Exponential tail, second moment, transfer-matrix gap, finite-size scaling collapse. |
| Channel | Scalar singlet, vector, charged sector, topological sector, screening channel. |

Without those ingredients, “the correlation length is large” is often under-specified. With them, it becomes a sharp statement about the infrared physics.

## Common pitfalls

**Forgetting the connected subtraction.** In an ordered phase, the full correlator may approach $\langle\mathcal O\rangle^2$. The correlation length of fluctuations is extracted from the connected correlator.

**Calling every infinite correlation length criticality.** Goldstone modes, photons, Fermi surfaces, and topological sectors can produce long-range behavior without an ordinary isolated critical point.

**Assuming all operators see the lightest state.** An operator only sees states with the right quantum numbers and nonzero overlap.

**Mixing screening lengths with particle masses.** At finite temperature, spatial correlators define screening masses. These need not equal real-time pole masses or zero-temperature particle masses.

**Ignoring the lattice spacing.** A large lattice correlation length $\xi/a$ is what allows a continuum limit. A large number in lattice units is not the same thing as a large physical length if $a$ is changing.

**Overfitting short distances.** The exponential form is an asymptotic statement. Short-distance data are contaminated by cutoff effects, heavier states, contact terms, and operator mixing.

**Treating topological phases as locally trivial.** Local connected correlators can all be short-ranged while the phase is still nontrivial because of line operators, boundary response, or ground-state structure on nontrivial manifolds.

## Relations to other pages

[Local Order Parameters](/nonperturbative-qft/order-parameters-diagnostics/local-order-parameters/) explains how one-point functions diagnose ordinary symmetry realization. Correlation length refines that information by asking how fluctuations decay. [Disorder Parameters](/nonperturbative-qft/order-parameters-diagnostics/disorder-parameters/) explains how defect insertions can have their own correlation lengths and long-distance behavior.

[Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) explains why $\xi/a\to\infty$ is the lattice route to continuum QFT. [Quantum Phase Transitions](/nonperturbative-qft/vacuum-structure-phases/quantum-phase-transitions/) explains why the divergence of $\xi$ controls universal scaling near zero-temperature transitions.

The next page, [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), turns the same physics into a spectral statement: exponential decay in Euclidean time reveals energy gaps.

## Research status

The relation between correlation length, transfer matrices, spectral gaps, and critical scaling is established. It is one of the central bridges between statistical mechanics, lattice field theory, and continuum QFT.

The research-level subtleties arise in systems where “the long distance scale” is not unique: gauge theories with screening, finite-temperature real-time dynamics, gapless phases without ordinary criticality, theories with line operators and generalized symmetries, theories with severe sign problems, and systems where analytic continuation from Euclidean data is ill-conditioned.

## Exercises

### Exercise 1: Correlation length from a transfer matrix

Suppose a transfer matrix has eigenvalues $\lambda_0>\lambda_1>\lambda_2>\cdots>0$. Show that a connected correlator with nonzero overlap with the first excited state decays as

$$
G_c(n)\sim \left(\frac{\lambda_1}{\lambda_0}\right)^n
$$

at large separation $n$, and find the correlation length in lattice units.

<details>
<summary><strong>Solution</strong></summary>

Insert a complete set of transfer-matrix eigenstates. The connected correlator removes the vacuum contribution. If the operator has nonzero matrix element to the first excited state, the leading term is

$$
G_c(n)\sim A\left(\frac{\lambda_1}{\lambda_0}\right)^n.
$$

Writing this as $Ae^{-n/\xi}$ gives

$$
\frac{1}{\xi}=-\log\left(\frac{\lambda_1}{\lambda_0}\right)
=\log\left(\frac{\lambda_0}{\lambda_1}\right).
$$

Thus

$$
\xi=\frac{1}{\log(\lambda_0/\lambda_1)}.
$$

</details>

### Exercise 2: Critical exponent from an RG eigenvalue

Let $t$ be the only relevant perturbation near a fixed point, with RG scaling $t\mapsto b^{y_t}t$. Use the scaling equation for $\xi$ to show that $\xi\sim |t|^{-\nu}$ with $\nu=1/y_t$.

<details>
<summary><strong>Solution</strong></summary>

The correlation length satisfies

$$
\xi(t)=b\,\xi(b^{y_t}t).
$$

Choose $b=|t|^{-1/y_t}$ so that $b^{y_t}t=\pm1$. Then

$$
\xi(t)=|t|^{-1/y_t}\xi(\pm1).
$$

The factor $\xi(\pm1)$ is nonuniversal but finite, so

$$
\xi(t)\sim |t|^{-1/y_t}.
$$

Therefore $\nu=1/y_t$.

</details>

### Exercise 3: Why the connected correlator matters

Let a source-selected ordered phase have $\langle\mathcal O\rangle=v\neq0$ and

$$
\langle\mathcal O(r)\mathcal O(0)\rangle
=v^2+Ae^{-r/\xi}.
$$

What correlation length would you infer from the full correlator at very large $r$? What should you do instead?

<details>
<summary><strong>Solution</strong></summary>

The full correlator approaches $v^2$, so it does not decay to zero. Trying to fit the full correlator to a pure exponential at very large $r$ is meaningless. The fluctuation length is extracted from the connected correlator

$$
G_c(r)=\langle\mathcal O(r)\mathcal O(0)\rangle-\langle\mathcal O\rangle^2
=Ae^{-r/\xi}.
$$

Thus the correlation length of fluctuations is $\xi$.

</details>

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the RG and critical-phenomena framework connecting fixed points, correlation lengths, and scaling exponents.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for correlation functions, critical exponents, Euclidean field theory, and the RG treatment of critical phenomena.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for the transfer-matrix relation between correlation length and Euclidean mass, and for critical correlators.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for correlation length in RG flows, quantum criticality, and condensed-matter field-theory examples.
- M. Srednicki, *Quantum Field Theory*, especially the spectral viewpoint on exact propagators and the relation between poles, thresholds, and physical masses.

## Version history

- **2026-06-26:** Initial polished page.
