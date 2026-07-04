---
title: "Lattice Regularization"
description: "Explains how a Euclidean spacetime lattice gives a nonperturbative ultraviolet regulator for scalar and gauge fields, and what must be checked before taking a continuum limit."
sidebar:
  label: "Lattice Regularization"
  order: 2
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut; Srednicki §82; Schwartz §25.5; Zinn-Justin; Polyakov."
topics:
  - lattice regularization
  - Euclidean lattice
  - Wilson action
  - link variables
  - plaquettes
  - transfer matrix
  - continuum limit
canonicalTopics:
  - lattice-regularization
  - euclidean-qft
  - wilson-action
  - lattice-gauge-theory
  - nonperturbative-definitions
researchStatus:
  established:
    - "Euclidean lattice regularization gives a concrete nonperturbative ultraviolet regulator for many scalar, spin, and vectorlike gauge theories."
  active:
    - "Chiral gauge theories, real-time observables, finite density, topology at nonzero lattice spacing, and some symmetry-preserving discretizations require specialized methods beyond the basic Wilson-lattice construction."
---

## Summary

Lattice regularization replaces continuous Euclidean spacetime by a discrete set of points separated by a lattice spacing $a$. In finite volume, the path integral becomes an ordinary finite-dimensional integral, or a finite-dimensional Grassmann integral, before any continuum limit is taken. That is the crucial nonperturbative gain: one first defines a finite object, then studies limits.

For a scalar field on a hypercubic lattice, a standard Euclidean action is

$$
S_a[\phi]
=a^d\sum_n\left[
\frac12\sum_{\mu=1}^d
\left(\frac{\phi_{n+\mu}-\phi_n}{a}\right)^2
+\frac12m_0^2\phi_n^2+\frac{\lambda_0}{4!}\phi_n^4
\right],
$$

where $n$ labels lattice sites and $n+\mu$ means the nearest-neighbor site in the $\mu$ direction. The finite-volume regulated partition function is

$$
Z_a=\int\prod_n d\phi_n\,e^{-S_a[\phi]}.
$$

For gauge theory, the basic variables are not gauge potentials at sites but group-valued link variables

$$
U_\mu(n)\in G,
$$

living on the oriented link from $n$ to $n+\mu$. The elementary gauge-invariant loop is the plaquette,

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\mu)U_\mu(n+\nu)^\dagger U_\nu(n)^\dagger,
$$

and the Wilson gauge action for $G=SU(N)$ is commonly written

$$
S_W[U]
=\beta\sum_p\left(1-\frac1N\operatorname{Re}\operatorname{tr}U_p\right),
\qquad
\beta=\frac{2N}{g_0^2}.
$$

The lattice is not the continuum theory. It is a regulator. The continuum QFT, when it exists, is obtained by tuning bare parameters as $a\to0$ so that physical correlation lengths, masses, and dimensionless ratios approach finite limits.

## Prerequisites

You should know the [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), the role of [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/), and the conventions in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). It helps to have seen Wilson loops, but the gauge-field construction is reviewed below.

## Core idea

A lattice regularization does three jobs at once.

1. It provides an ultraviolet cutoff of order $1/a$ by removing arbitrarily short distances.
2. It turns the Euclidean path integral into a well-defined finite-volume statistical-mechanics problem.
3. It preserves selected exact structures, especially locality and gauge invariance, so that the desired continuum symmetries can reappear at long distances.

The tradeoff is equally important. A hypercubic lattice breaks continuous translations, rotations, and Lorentz symmetry at nonzero $a$. For scalar fields this is usually acceptable because these symmetries can re-emerge in the continuum limit. For gauge theories, the lattice is especially powerful because exact gauge invariance can be kept at every nonzero lattice spacing by using link variables instead of gauge potentials.

The right mental picture is not

$$
\text{lattice theory} = \text{continuum theory with uglier notation}.
$$

It is

$$
\text{continuum QFT}
=\lim_{a\to0}\text{a carefully tuned family of regulated lattice systems}.
$$

## Setup and conventions

We work in $d$-dimensional Euclidean spacetime. A hypercubic lattice has sites

$$
x=a n,
\qquad
n=(n_1,\ldots,n_d)\in\mathbb Z^d,
$$

usually with periodic boundary conditions in finite volume. The physical side length is

$$
L=N_s a,
$$

where $N_s$ is the number of sites in each direction. Unit lattice vectors are denoted by $\mu$ when no confusion is likely; thus $n+\mu$ means $n+\hat e_\mu$.

The Brillouin zone for lattice momenta is

$$
p_\mu\in\left(-\frac{\pi}{a},\frac{\pi}{a}\right],
$$

so $1/a$ is the ultraviolet scale. Numerical constants such as $\pi/a$ depend on the precise cutoff convention, but the physical statement is invariant: momenta much larger than $1/a$ do not exist in the regulated theory.

We use Euclidean weights $e^{-S_a}$. Gauge-field generators are normalized as in the volume conventions,

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

and link variables near the continuum limit are written schematically as

$$
U_\mu(n)=\exp\!\left(iag_0 A_\mu(x)\right),
\qquad x=an.
$$

The exact placement of $A_\mu$ along the link only affects higher-order lattice artifacts.

## Scalar fields on a lattice

For a scalar field, the continuum derivative is replaced by a finite difference. The forward difference is

$$
\nabla_\mu^+ \phi_n=\frac{\phi_{n+\mu}-\phi_n}{a},
$$

and the simplest lattice kinetic term is

$$
\frac12a^d\sum_{n,\mu}(\nabla_\mu^+\phi_n)^2.
$$

This term is local: it only couples nearest-neighbor sites. It is also positive in Euclidean signature. For the free scalar field,

$$
S_a^{(2)}=\frac12a^d\sum_n\left[\sum_\mu(\nabla_\mu^+\phi_n)^2+m_0^2\phi_n^2\right],
$$

the momentum-space propagator is

$$
G_a(p)=\frac{1}{\widehat p^{\,2}+m_0^2},
\qquad
\widehat p^{\,2}=\frac4{a^2}\sum_{\mu=1}^d\sin^2\left(\frac{ap_\mu}{2}\right).
$$

At small lattice momentum, $ap_\mu\ll1$,

$$
\widehat p^{\,2}=p^2+O(a^2p^4),
$$

so the continuum propagator is recovered for long-wavelength modes. Near the edge of the Brillouin zone, the expression differs strongly from $p^2$; that is not a bug. It is the cutoff doing its job.

The same action also makes clear why lattice units are dangerous if left uninterpreted. A measured mass appears as the dimensionless number

$$
am_{\mathrm{lat}}.
$$

To obtain a continuum QFT with physical mass $M$, one must take $aM\to0$ while keeping $M$ fixed in physical units. Equivalently, the correlation length in lattice units must diverge.

## Gauge fields live on links

For gauge theory, putting $A_\mu(n)$ directly on lattice sites obscures gauge invariance. The natural object is the parallel transporter along a link,

$$
U_\mu(n)\in G.
$$

A lattice gauge transformation is a choice of group element $\Omega(n)\in G$ at every site. Matter fields in the fundamental representation transform as

$$
\psi(n)\mapsto\Omega(n)\psi(n),
$$

while link variables transform as

$$
U_\mu(n)
\mapsto
\Omega(n)U_\mu(n)\Omega(n+\mu)^\dagger.
$$

This rule says exactly what a parallel transporter should say: it carries a color vector from one site to the next, so it must transform at both endpoints.

A nearest-neighbor gauge-invariant matter hopping term is therefore

$$
\psi(n)^\dagger U_\mu(n)\psi(n+\mu),
$$

with spinor and representation details suppressed. A closed product of links is gauge invariant after taking a trace. The smallest nontrivial loop is the plaquette,

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\mu)U_\mu(n+\nu)^\dagger U_\nu(n)^\dagger.
$$

Under a gauge transformation,

$$
U_{\mu\nu}(n)\mapsto\Omega(n)U_{\mu\nu}(n)\Omega(n)^\dagger,
$$

so $\operatorname{tr}U_{\mu\nu}(n)$ is gauge invariant.

<figure class="doc-figure" style="--figure-width: 36rem;">

![A hypercubic lattice with site fields, link variables, and an elementary plaquette.](/figures/nonperturbative-qft/lattice-regularization-elements.svg)

<figcaption>

The basic data of lattice regularization. Scalar or matter fields live on sites, gauge variables $U_\mu(n)$ live on links, and the elementary gauge-invariant curvature probe is the plaquette $U_{\mu\nu}(n)$.

</figcaption>
</figure>

## Wilson gauge action

The Wilson gauge action is built from plaquettes:

$$
S_W[U]
=\beta\sum_p\left(1-\frac1N\operatorname{Re}\operatorname{tr}U_p\right),
\qquad
\beta=\frac{2N}{g_0^2}
$$

for $SU(N)$ in the fundamental representation. The partition function in finite volume is

$$
Z_a=\int\prod_{\ell}dU_\ell\,e^{-S_W[U]},
$$

where $dU_\ell$ is the Haar measure on the compact gauge group for each link $\ell$.

To see the continuum limit, insert

$$
U_\mu(n)=\exp\!\left(iag_0 A_\mu(x)\right).
$$

For smooth fields,

$$
U_{\mu\nu}(n)
=\exp\!\left(ia^2g_0 F_{\mu\nu}(x)+O(a^3)\right).
$$

Using $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$, the plaquette action becomes the Yang–Mills action plus lattice artifacts:

$$
S_W[U]
\longrightarrow
\frac14\int d^dx\,F_{\mu\nu}^aF_{\mu\nu}^a
+O(a^2)
$$

in four dimensions, after the usual continuum normalization is restored. The precise form of the $O(a^2)$ corrections depends on the lattice action. Improved actions add larger loops to reduce these artifacts while preserving gauge invariance.

## Transfer matrix and spectra

A Euclidean lattice with one direction designated as time can often be rewritten in terms of a transfer matrix $T$. Roughly,

$$
T\sim e^{-aH},
$$

so repeated Euclidean-time steps project onto low-energy states. For an operator $\mathcal O$ with the desired quantum numbers, the connected two-point function has the spectral form

$$
C(n_t)
=\langle \mathcal O(n_t)\mathcal O(0)\rangle_c
=\sum_k |\langle0|\mathcal O|k\rangle|^2 e^{-aE_k n_t}.
$$

At large Euclidean time separation, the lightest state with those quantum numbers dominates:

$$
C(n_t)\sim A e^{-aE_0n_t}.
$$

This is why lattice calculations are naturally suited to masses, string tensions, matrix elements, condensates, thermodynamics, and Euclidean correlation functions.

There is a caveat. A positive transfer matrix is tied to reflection positivity. Many standard lattice actions have it. Some improved, nonlocal, gauge-fixed, or otherwise engineered actions may lose it at finite $a$, even if they are intended to recover a sensible continuum theory. Reflection positivity is not decorative bookkeeping; it is the Euclidean shadow of a positive-norm Hilbert space.

## What the lattice preserves and what it breaks

The lattice preserves some structures exactly and sacrifices others temporarily.

| Structure | At nonzero lattice spacing | Continuum expectation |
|---|---|---|
| Locality | Preserved if couplings have finite range or decay rapidly. | Required for local QFT. |
| Gauge invariance | Can be exact through link variables. | Required for gauge theory. |
| Compact gauge group | Built into link integration. | Encodes global gauge data and line operators. |
| Translations | Reduced to discrete translations. | Continuous translations should re-emerge. |
| Rotations or Lorentz symmetry | Reduced to hypercubic symmetry. | Restored in the continuum limit if the right universality class is reached. |
| Chiral symmetry | Often broken by simple fermion discretizations. | Requires special formulations or tuning. |
| Topological sectors | Subtle for rough lattice fields. | Smooth-sector topology emerges or is imposed through refined definitions. |

The last two entries are frequent sources of confusion. Gauge invariance is easy to preserve on the lattice; chiral symmetry and topology are harder. Naive fermions produce doublers, Wilson fermions remove them by breaking chiral symmetry, staggered fermions keep a remnant structure, and overlap or domain-wall fermions implement a more refined version of lattice chirality. Those details belong to later lattice-fermion pages, but the moral belongs here: preserving the right symmetries at finite cutoff can be a deep part of the definition.

## What can and cannot be computed directly

The lattice is exceptionally good at Euclidean, nonperturbative, finite-volume questions. Typical targets include:

| Observable | Lattice strategy |
|---|---|
| Mass gap | Large-distance decay of Euclidean two-point functions. |
| String tension | Large Wilson loops or flux-tube energies. |
| Condensates | Expectation values of local or renormalized composite operators. |
| Thermodynamics | Compact Euclidean time with circumference $\beta$. |
| Matrix elements | Correlation functions with operator insertions. |
| Phase structure | Order parameters, susceptibilities, finite-size scaling, and line operators. |

Several important quantities are not directly Euclidean static observables. Scattering amplitudes require finite-volume reconstruction or analytic continuation. Real-time response functions require ill-conditioned analytic continuation or real-time methods. Finite-density theories often have a complex measure. Chiral gauge theories require special regulator constructions. None of these limitations makes the lattice weak. They mark exactly where a Euclidean probability-based regulator is most and least adapted to the physics.

## Common pitfalls

**Taking $a\to0$ at fixed bare parameters.** The continuum limit is usually not obtained by holding the bare lattice action fixed. One must tune the bare parameters so that selected physical observables remain finite while the cutoff is removed.

**Confusing lattice units with physical units.** A lattice calculation may output $am$, $a^2\sigma$, or $L/a$. These are dimensionless regulator quantities. Physics lives in dimensionless ratios such as $m_1/m_2$ or in dimensionful quantities after one scale has been fixed.

**Putting gauge fields on sites.** The gauge-invariant lattice object is the link variable $U_\mu(n)$, not the continuum potential $A_\mu(x)$ by itself. The plaquette, not a finite difference of $A_\mu$, is the fundamental curvature probe.

**Expecting Lorentz symmetry at finite lattice spacing.** A hypercubic lattice does not have continuous Euclidean rotational symmetry. The claim is that the symmetry is restored in long-distance observables as $a\to0$, provided the regulator is in the right universality class.

**Assuming all discretizations are harmless.** Irrelevant operators die in the continuum limit, but relevant symmetry-breaking terms must be forbidden or tuned away. This is why chiral symmetry, supersymmetry, and some topological features can be hard to preserve on the lattice.

## Relations to other pages

- [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) explains why a positive Euclidean weight and reflection positivity are central to nonperturbative definitions.
- [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) explains how the regulated family of lattice theories becomes a continuum QFT.
- [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) explains the Wilson loops, spectra, and correlators that lattice regularization computes well.
- [Semiclassical versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/) distinguishes lattice strong-coupling expansions from weak-coupling semiclassics.

## Research status

Lattice regularization is textbook-standard as a nonperturbative regulator for scalar theories, spin systems, pure Yang–Mills theory, and vectorlike gauge theories such as QCD. Its practical power comes from the combination of exact gauge invariance, locality, finite-volume well-definedness, and systematically improvable continuum extrapolations.

The frontier is not whether lattices are useful. The frontier is how far the method can be pushed while preserving the desired physics: chiral gauge theories, supersymmetric theories, finite-density systems, real-time dynamics, topological terms with complex weights, and theories whose continuum limit is not yet understood.

## Exercises

### Exercise 1: Recover the continuum scalar kinetic term

Show that for a smooth scalar field $\phi(x)$ with $x=an$,

$$
\frac{\phi_{n+\mu}-\phi_n}{a}
=\partial_\mu\phi(x)+O(a).
$$

Then show that the lattice kinetic term approaches $\frac12\int d^dx\,(\partial_\mu\phi)^2$ as $a\to0$.

<details>
<summary><strong>Solution</strong></summary>

Taylor expand:

$$
\phi(x+a\hat e_\mu)=\phi(x)+a\partial_\mu\phi(x)+\frac{a^2}{2}\partial_\mu^2\phi(x)+O(a^3).
$$

Therefore

$$
\frac{\phi_{n+\mu}-\phi_n}{a}
=\partial_\mu\phi(x)+O(a).
$$

Also $a^d\sum_n$ is the Riemann-sum approximation to $\int d^dx$. Thus

$$
\frac12a^d\sum_{n,\mu}\left(\frac{\phi_{n+\mu}-\phi_n}{a}\right)^2
\to
\frac12\int d^dx\sum_\mu(\partial_\mu\phi)^2.
$$

</details>

### Exercise 2: Gauge transformation of a plaquette

Using

$$
U_\mu(n)\mapsto\Omega(n)U_\mu(n)\Omega(n+\mu)^\dagger,
$$

show that

$$
U_{\mu\nu}(n)\mapsto\Omega(n)U_{\mu\nu}(n)\Omega(n)^\dagger.
$$

Conclude that $\operatorname{tr}U_{\mu\nu}(n)$ is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

Insert the transformation rule into

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\mu)U_\mu(n+\nu)^\dagger U_\nu(n)^\dagger.
$$

Adjacent factors such as $\Omega(n+\mu)^\dagger\Omega(n+\mu)$ cancel. All internal site transformations cancel pairwise, leaving only

$$
U_{\mu\nu}(n)\mapsto\Omega(n)U_{\mu\nu}(n)\Omega(n)^\dagger.
$$

Taking a trace removes the remaining conjugation.

</details>

### Exercise 3: Effective mass from a Euclidean correlator

Suppose a lattice correlator is dominated at large time by one state,

$$
C(n_t)=A e^{-aE n_t}.
$$

Show that the effective mass estimator

$$
am_{\mathrm{eff}}(n_t)=\log\frac{C(n_t)}{C(n_t+1)}
$$

approaches $aE$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the large-time form:

$$
\log\frac{C(n_t)}{C(n_t+1)}
=\log\frac{Ae^{-aE n_t}}{Ae^{-aE(n_t+1)}}
=\log e^{aE}=aE.
$$

If several states contribute, this expression approaches $aE_0$ only once the excited-state terms are sufficiently suppressed.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, section 82, for Wilson loops, lattice gauge theory, strong coupling, and confinement.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, section 25.5, for a compact introduction to lattice gauge theory and link variables.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the Euclidean field-integral and statistical-mechanics viewpoint.

### Deeper references

- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the Wilsonian relation between lattice systems, critical points, and continuum QFT.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling expansions, compact gauge fields, confinement criteria, and loop variables.
- J. Smit, *Introduction to Quantum Fields on a Lattice*, and C. Gattringer and C. B. Lang, *Quantum Chromodynamics on the Lattice*, for dedicated lattice-QFT treatments.

## Version history

- **2026-06-25:** Initial polished page.
