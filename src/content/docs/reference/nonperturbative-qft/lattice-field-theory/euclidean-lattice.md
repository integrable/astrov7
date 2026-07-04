---
title: "Euclidean Lattice"
description: "Defines the Euclidean spacetime lattice as a nonperturbative regulator, including sites, finite differences, lattice momenta, finite volume, correlators, and continuum-limit scaling."
sidebar:
  label: "Euclidean Lattice"
  order: 1
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut; Zinn-Justin; Srednicki; Schwartz; Rothe; Gattringer–Lang; Montvay–Münster; Altland–Simons."
topics:
  - Euclidean lattice
  - lattice spacing
  - finite volume
  - lattice momenta
  - finite differences
  - scalar lattice action
  - correlation length
  - continuum limit
  - reflection positivity
  - Brillouin zone
canonicalTopics:
  - nonperturbative-qft
  - lattice-field-theory
  - euclidean-lattice
  - lattice-regularization
  - continuum-limit
  - finite-volume-qft
researchStatus:
  established:
    - "A Euclidean lattice in finite volume gives a finite-dimensional regulator for many bosonic QFT path integrals and a starting point for nonperturbative continuum limits."
  active:
    - "The choice of lattice action, improvement scheme, boundary condition, fermion discretization, and real-time or finite-density continuation remains highly problem-dependent."
---

## Summary

A **Euclidean lattice** replaces continuous Euclidean spacetime by a discrete set of points

$$
x=a n,
\qquad n\in \mathbb Z^d,
$$

or, in finite volume,

$$
n_\mu=0,1,\ldots,N_\mu-1,
\qquad L_\mu=N_\mu a.
$$

The lattice spacing $a$ is a short-distance cutoff. Finite $N_\mu$ is an infrared cutoff. A field integral that was formal in the continuum becomes an ordinary finite-dimensional integral or sum in finite volume. That is the first reason the lattice is a serious nonperturbative definition rather than just a numerical mesh.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Anatomy of a Euclidean lattice: sites carry scalar fields, links carry gauge transporters, plaquettes form elementary loops, and momenta live in the Brillouin zone.](/figures/nonperturbative-qft/euclidean-lattice-anatomy.svg)

<figcaption>

The Euclidean lattice has both position-space and momentum-space anatomy. In position space, scalar fields live on sites, gauge fields live on links, and local gauge dynamics is built from plaquettes. In momentum space, modes live inside the Brillouin zone, so the lattice spacing supplies an ultraviolet cutoff of order $\pi/a$.

</figcaption>
</figure>

The price is also clear. The lattice theory at nonzero $a$ is not the continuum theory. Translation and rotation symmetry are reduced, derivatives become finite differences, momenta live in a Brillouin zone, and local actions contain lattice artifacts. The continuum QFT is recovered only if one can tune bare parameters so that physical long-distance quantities survive as

$$
a\to0,
\qquad \frac{\xi}{a}\to\infty,
$$

where $\xi$ is a physical correlation length.

## Prerequisites

Read [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), and [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) first.

It also helps to know [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/) and [Mass Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), because the lattice continuum limit is most naturally phrased in terms of long correlation lengths in lattice units.

## Core idea

The Euclidean continuum path integral has the schematic form

$$
Z=\int [d\phi] e^{-S_E[\phi]}.
$$

On a finite lattice, this becomes

$$
Z_a=\int \prod_n d\phi_n\, e^{-S_a[\phi]},
$$

for bosonic site fields. If the theory has discrete or compact degrees of freedom, the integral may be a finite sum or a product of compact group integrals. For gauge fields, the variables are group elements on links and the measure is a product of Haar measures.

This does three things at once:

1. it regulates ultraviolet modes because momenta are bounded by the Brillouin zone;
2. it regulates infrared physics because finite volume makes the number of degrees of freedom finite;
3. it turns Euclidean QFT into a statistical system whose correlation functions can be defined without perturbation theory.

A lattice definition is therefore a family of finite systems labeled by $a$, $N_\mu$, and bare couplings. The QFT is not one member of the family. It is the scaling limit of the family, if that limit exists.

## Setup and conventions

Take a $d$-dimensional hypercubic Euclidean lattice. A site is labeled by

$$
n=(n_1,\ldots,n_d),
\qquad x_n=a n.
$$

The unit vector in direction $\mu$ is written $\hat\mu$, so the neighboring site is

$$
n+\hat\mu.
$$

A finite periodic lattice has

$$
n_\mu\sim n_\mu+N_\mu,
\qquad L_\mu=N_\mu a.
$$

Periodic boundary conditions are common for bosons and gauge fields. Fermions at finite temperature are antiperiodic in Euclidean time and usually periodic in spatial directions, though other choices are used for specific problems.

The continuum integral is replaced by

$$
\int d^d x\, f(x)
\quad\longrightarrow\quad
 a^d\sum_n f_n.
$$

The forward and backward finite differences are

$$
\nabla^+_\mu \phi_n=\frac{\phi_{n+\hat\mu}-\phi_n}{a},
\qquad
\nabla^-_\mu \phi_n=\frac{\phi_n-\phi_{n-\hat\mu}}{a}.
$$

The symmetric lattice Laplacian is

$$
-\Delta_a\phi_n
=\frac{1}{a^2}\sum_\mu
\left(2\phi_n-\phi_{n+\hat\mu}-\phi_{n-\hat\mu}\right).
$$

This is local, respects lattice translations, and becomes $-\partial^2\phi$ at long wavelength.

## Scalar field example

A standard Euclidean lattice scalar action is

$$
S_a[\phi]
=a^d\sum_n\left[
\frac12\sum_\mu\left(\frac{\phi_{n+\hat\mu}-\phi_n}{a}\right)^2
+\frac12 m_0^2\phi_n^2
+\frac{\lambda_0}{4!}\phi_n^4
\right].
$$

This is the direct finite-difference version of

$$
S_E[\phi]=\int d^d x\left[
\frac12(\partial_\mu\phi)^2+\frac12m_0^2\phi^2+\frac{\lambda_0}{4!}\phi^4
\right].
$$

The bare parameters $m_0^2$ and $\lambda_0$ depend on the cutoff. They are not automatically the physical mass and coupling. The continuum limit is obtained by tuning bare parameters so that dimensionless long-distance observables approach finite values.

A useful dimensionless version rescales the field and parameters so that the action is written entirely in lattice units. That is often better for simulation, but the above form makes the continuum interpretation transparent.

## Momentum space and the Brillouin zone

On a finite periodic lattice, momenta are discrete:

$$
p_\mu=\frac{2\pi k_\mu}{L_\mu},
\qquad k_\mu=0,1,\ldots,N_\mu-1.
$$

Equivalently, one may choose representatives inside the first Brillouin zone,

$$
-\frac{\pi}{a}<p_\mu\le \frac{\pi}{a}.
$$

For the free scalar theory, the lattice kinetic operator has eigenvalue

$$
\widehat p^{\,2}
=\frac{4}{a^2}\sum_\mu \sin^2\left(\frac{a p_\mu}{2}\right).
$$

The free lattice propagator is therefore

$$
G_a(p)=\frac{1}{\widehat p^{\,2}+m_0^2}.
$$

At small $a p_\mu$,

$$
\widehat p^{\,2}=p^2+O(a^2p^4),
$$

so the continuum propagator is recovered at long wavelengths. At momenta near the edge of the Brillouin zone, however, the lattice theory differs strongly from the continuum theory. That is the point: high-momentum modes are regulated.

## Correlation functions and spectra

Euclidean lattice correlation functions are defined by finite-dimensional averages:

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_a
=\frac{1}{Z_a}\int \prod_n d\phi_n\,
\mathcal O_1\cdots \mathcal O_k\,e^{-S_a[\phi]}.
$$

For a translation-invariant scalar theory, the connected two-point function often decays at large separation as

$$
G_c(n)\sim \frac{e^{-|n|/\xi_a}}{|n|^{(d-1)/2}},
$$

away from criticality, where $\xi_a$ is the correlation length measured in lattice spacings. The physical correlation length is

$$
\xi_{\rm phys}=a\xi_a.
$$

If a Euclidean time direction is singled out and reflection positivity holds, correlation functions have spectral decompositions. A zero-momentum two-point function behaves at large Euclidean time as

$$
C(\tau)=\sum_{\mathbf x}\langle \mathcal O(\tau,\mathbf x)\mathcal O(0,\mathbf0)\rangle
\sim A e^{-E_0\tau a}+\cdots.
$$

Thus lattice energies are extracted from exponential decay. In lattice units,

$$
aE_0=-\lim_{n_\tau\to\infty}\log\frac{C(n_\tau+1)}{C(n_\tau)}.
$$

This is the basic reason Euclidean lattice methods are so powerful for masses and spectra. The scalar version of this story is developed in [Lattice Scalar Field Theory](/nonperturbative-qft/lattice-field-theory/lattice-scalar-field-theory/).

## Gauge fields preview

For scalar fields, the variable sits on a site, as explained in [Lattice Scalar Field Theory](/nonperturbative-qft/lattice-field-theory/lattice-scalar-field-theory/). For gauge fields, the natural variable sits on an oriented link, as developed in [Lattice Gauge Fields](/nonperturbative-qft/lattice-field-theory/lattice-gauge-fields/):

$$
U_\mu(n)\in G.
$$

It is a parallel transporter from $n$ to $n+\hat\mu$. Under a lattice gauge transformation $g(n)\in G$,

$$
U_\mu(n)\to g(n)U_\mu(n)g(n+\hat\mu)^{-1}.
$$

The elementary gauge-invariant loop is the plaquette

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\hat\mu)U_\mu(n+\hat\nu)^{-1}U_\nu(n)^{-1}.
$$

For a smooth continuum gauge field,

$$
U_\mu(n)\approx \exp\left(i a A_\mu(x_n)\right),
$$

and the plaquette approximates the field strength:

$$
U_{\mu\nu}(n)\approx \exp\left(i a^2 F_{\mu\nu}(x_n)+O(a^3)\right).
$$

This is why lattice gauge theory preserves exact gauge invariance at finite $a$: gauge fields are not represented by additive components $A_\mu$ directly, but by group-valued transporters. See [Lattice Gauge Fields](/nonperturbative-qft/lattice-field-theory/lattice-gauge-fields/) for the full link-variable construction.

## Continuum limit

A lattice action is a regulator. A continuum QFT is obtained from a limit. The clean scaling condition is

$$
a\to0
\quad\text{with physical quantities fixed.}
$$

Equivalently, if the theory has a mass gap $m$, then

$$
am\to0,
\qquad \xi_a=\frac1{am}\to\infty.
$$

This means the continuum limit is controlled by a critical point or critical surface of the lattice statistical system. The lattice correlation length in units of $a$ must diverge so that the lattice spacing becomes invisible compared with the physics being measured.

A typical continuum-extrapolation strategy has the form

$$
\mathcal O(a)=\mathcal O_{\rm cont}+c_1 a^p+c_2 a^{p+1}+\cdots,
$$

where $p$ depends on the lattice action and improvement scheme. The exponents and coefficients are not magic; they reflect irrelevant operators allowed by lattice symmetries.

## Finite-volume limits

Finite volume is not just a nuisance. It is also part of the definition. In finite volume, the spectrum is discrete, tunneling between would-be degenerate vacua can occur, and true spontaneous symmetry breaking is subtle.

For massive theories, many finite-volume corrections scale like

$$
e^{-mL},
$$

up to powers of $L$, when $mL\gg1$. For massless theories or near-critical systems, finite-size scaling is more delicate and often more useful. Critical behavior is commonly studied through the dependence of observables on $L/\xi$.

For thermal field theory, the Euclidean time direction has length

$$
\beta=\frac1T=N_\tau a,
$$

with boundary conditions fixed by statistics: periodic for bosons and antiperiodic for fermions. Thermal lattice field theory is therefore finite-size physics in the Euclidean time direction.

## Positivity and the sign problem

When the Euclidean action is real and bounded below, $e^{-S_a}$ can be interpreted as a probability weight. This enables importance sampling and makes Monte Carlo methods practical.

But positivity is not automatic. The effective weight can become complex or indefinite, for example in real-time path integrals, in many finite-density fermion systems, in theta-term problems, or after integrating out fermions with a complex determinant. Then the expression

$$
Z_a=\int d\Phi\,e^{-S_a[\Phi]}
$$

is still formally defined, but it is no longer an ordinary probability average. This is the **sign problem**. It is not a mere coding inefficiency; it is a structural obstacle to importance sampling.

Reflection positivity is another important condition. It is the Euclidean property that allows reconstruction of a Hilbert space with positive norm and a Hamiltonian bounded below. A lattice action can look reasonable as a finite statistical model while failing this property.

## How to check a Euclidean lattice definition

A good lattice definition should pass several checks.

First, the action should be local in lattice units. Couplings should connect nearby sites, links, or plaquettes, except when a controlled nonlocal effective action is being used.

Second, it should preserve the symmetries one cannot afford to break. Gauge invariance is usually preserved exactly by link variables. Translation and rotation symmetry are reduced to lattice subgroups and should re-emerge in the continuum limit. Chiral symmetry for fermions is subtle and deserves its own pages.

Third, the continuum expansion should reproduce the intended target action. For example,

$$
\widehat p^{\,2}=p^2+O(a^2p^4)
$$

for the scalar kinetic term, and

$$
\operatorname{Re}\operatorname{tr}\left(1-U_{\mu\nu}\right)
\propto a^4\operatorname{tr}F_{\mu\nu}^2+O(a^6)
$$

for the gauge plaquette.

Fourth, long-distance observables should have a scaling window where physical ratios become independent of $a$ up to controlled lattice artifacts.

## Common pitfalls

**Calling $a\to0$ a limit at fixed bare parameters.** Usually that gives either a trivial theory or no finite physics. The continuum limit is a tuned path in bare-coupling space.

**Confusing lattice units with physical units.** A measured mass $am=0.2$ is dimensionless. The physical mass is obtained only after setting the scale.

**Assuming the finite lattice shows spontaneous symmetry breaking directly.** At finite volume, exact symmetries are not spontaneously broken in the naive infinite-volume sense. Order parameters require careful source, volume, and limit prescriptions.

**Treating the Brillouin-zone edge as physical.** Physics near $p_\mu\sim\pi/a$ is regulator physics unless the lattice itself is the microscopic system of interest.

**Trusting a discretization only because it has the right continuum-looking formula.** Reflection positivity, gauge invariance, locality, species doubling, and symmetry-breaking artifacts can matter as much as naive Taylor expansion.


## Relations to other pages

- [Lattice Field Theory](/nonperturbative-qft/lattice-field-theory/) gives the chapter reading path and explains where this page sits in the lattice-methods arc.
- [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/) explains why a finite lattice is a nonperturbative regulator, while this page fixes the geometry and notation used later.
- [Lattice Scalar Field Theory](/nonperturbative-qft/lattice-field-theory/lattice-scalar-field-theory/) uses the finite differences and Brillouin-zone notation here to define scalar site-field actions and propagators.
- [Lattice Gauge Fields](/nonperturbative-qft/lattice-field-theory/lattice-gauge-fields/) promotes links and plaquettes from geometric cells to compact gauge variables and Wilson-loop observables.
- [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) gives the RG logic behind tuning toward a critical surface.
- [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) explains the positivity condition behind transfer matrices and spectral extraction.
- [Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/) uses plaquettes and Wilson loops to derive an area law at strong bare coupling.
- [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/) uses Euclidean correlation functions in the same spectral-extraction logic.

## Research status

The Euclidean lattice construction is established and central. It is the standard nonperturbative regulator for many bosonic and vectorlike gauge theories, and it underlies modern quantitative lattice QCD.

The active issues begin when the simple probability-measure picture breaks. Chiral gauge theories, finite-density systems, real-time observables, topology at fine lattice spacing, and efficient fermion algorithms all require specialized ideas. Precision lattice work also depends on systematic control of finite-volume effects, continuum extrapolations, operator matching, scale setting, and algorithmic autocorrelations.

## Exercises

### Exercise 1: Lattice kinetic eigenvalue

Show that the lattice Laplacian

$$
-\Delta_a\phi_n
=\frac1{a^2}\sum_\mu\left(2\phi_n-\phi_{n+\hat\mu}-\phi_{n-\hat\mu}\right)
$$

has eigenvalue $\widehat p^{\,2}=\frac4{a^2}\sum_\mu\sin^2(ap_\mu/2)$ on a plane wave $\phi_n=e^{ip\cdot an}$.

<details>
<summary><strong>Solution</strong></summary>

For the plane wave,

$$
\phi_{n+\hat\mu}=e^{ia p_\mu}\phi_n,
\qquad
\phi_{n-\hat\mu}=e^{-ia p_\mu}\phi_n.
$$

Therefore

$$
-\Delta_a\phi_n
=\frac1{a^2}\sum_\mu
\left(2-e^{iap_\mu}-e^{-iap_\mu}\right)\phi_n.
$$

Using $2-e^{ix}-e^{-ix}=2-2\cos x=4\sin^2(x/2)$ gives

$$
-\Delta_a\phi_n
=\left[\frac4{a^2}\sum_\mu\sin^2\left(\frac{a p_\mu}{2}\right)\right]\phi_n.
$$

So the eigenvalue is $\widehat p^{\,2}$.

</details>

### Exercise 2: Continuum expansion of the lattice momentum

Show that $\widehat p^{\,2}=p^2+O(a^2p^4)$ at small $a p_\mu$.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\sin\left(\frac{a p_\mu}{2}\right)
=\frac{a p_\mu}{2}-\frac1{6}\left(\frac{a p_\mu}{2}\right)^3+O(a^5p_\mu^5).
$$

Then

$$
\frac4{a^2}\sin^2\left(\frac{a p_\mu}{2}\right)
=p_\mu^2-\frac{a^2}{12}p_\mu^4+O(a^4p_\mu^6).
$$

Summing over $\mu$ gives

$$
\widehat p^{\,2}=p^2-\frac{a^2}{12}\sum_\mu p_\mu^4+O(a^4p^6),
$$

so the leading continuum limit is $p^2$.

</details>

### Exercise 3: Correlation length and continuum scaling

Suppose a lattice simulation measures a dimensionless mass $am=0.25$. What is the correlation length in lattice units? What must happen to $am$ along a continuum-limit trajectory if the physical mass is held fixed?

<details>
<summary><strong>Solution</strong></summary>

For a massive particle,

$$
\xi_a=\frac1{am}.
$$

Thus $am=0.25$ gives

$$
\xi_a=4.
$$

If the physical mass $m$ is held fixed while $a\to0$, then

$$
am\to0,
\qquad \xi_a=\frac1{am}\to\infty.
$$

The continuum limit is therefore a long-correlation-length limit in lattice units.

</details>

### Exercise 4: Finite-volume momentum spacing

For a periodic lattice with $N$ sites in one direction and spacing $a$, show that the momentum spacing is $2\pi/L$ and that the largest independent momenta are of order $\pi/a$.

<details>
<summary><strong>Solution</strong></summary>

The physical length is

$$
L=Na.
$$

Periodic boundary conditions require

$$
e^{ipL}=1,
$$

so

$$
p=\frac{2\pi k}{L},
\qquad k\in\mathbb Z.
$$

Thus the momentum spacing is $2\pi/L$. Because lattice momenta differing by $2\pi/a$ are equivalent on lattice sites, independent representatives can be chosen in

$$
-\frac{\pi}{a} < p\le \frac{\pi}{a}.
$$

So the ultraviolet cutoff is of order $\pi/a$.

</details>

## References

### Standard first pass

- J. B. Kogut, “An Introduction to Lattice Gauge Theory and Spin Systems,” for the classic formulation of lattice gauge variables, transfer-matrix logic, spin-system analogies, and confinement diagnostics.
- M. Creutz, *Quarks, Gluons and Lattices*, for a physically transparent introduction to lattice QCD and gauge-field variables.
- H. J. Rothe, *Lattice Gauge Theories*, for a standard systematic treatment.

### Deeper references

- I. Montvay and G. Münster, *Quantum Fields on a Lattice*, for lattice fermions, gauge actions, and numerical methods.
- C. Gattringer and C. B. Lang, *Quantum Chromodynamics on the Lattice*, for QCD-oriented lattice foundations.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean field integrals, lattice regularization, critical behavior, and continuum limits.
- M. Srednicki, *Quantum Field Theory*, especially the discussion of Wilson loops, lattice theory, and confinement.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the introductory lattice gauge-theory discussion in Yang–Mills theory.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for lattice gauge theory, link variables, plaquette actions, and the bridge to condensed-matter gauge systems.

## Version history

- **2026-06-28:** Initial polished page introducing Euclidean lattice geometry, finite differences, lattice momenta, scalar actions, gauge-link preview, correlators, and continuum-limit scaling. Updated relations after the scalar-field and gauge-field lattice pages were added.
- **2026-06-28:** Added relations to Lattice Scalar Field Theory and Lattice Gauge Fields.
