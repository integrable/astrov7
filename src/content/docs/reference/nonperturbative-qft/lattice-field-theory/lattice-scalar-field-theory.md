---
title: "Lattice Scalar Field Theory"
description: "Defines scalar fields on a Euclidean lattice, including finite-difference actions, lattice propagators, critical tuning, correlation lengths, and continuum limits."
sidebar:
  label: "Lattice Scalar Fields"
  order: 2
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut; Zinn-Justin; Srednicki; Schwartz; Rothe; Gattringer–Lang; Montvay–Münster."
topics:
  - lattice scalar field theory
  - finite differences
  - lattice propagator
  - phi-four theory
  - Ising universality
  - correlation length
  - critical point
  - continuum limit
  - reflection positivity
canonicalTopics:
  - nonperturbative-qft
  - lattice-field-theory
  - lattice-scalar-field-theory
  - euclidean-lattice
  - continuum-limit
  - correlation-length
researchStatus:
  established:
    - "Scalar lattice field theory is a standard nonperturbative regulator and statistical-mechanics realization of scalar QFT and universality classes."
  active:
    - "Precision continuum extrapolation, improvement, triviality in four-dimensional scalar theories, and scalar sectors coupled to gauge fields remain context-dependent research issues."
---

## Summary

A **lattice scalar field theory** assigns a scalar variable $\phi_n$ to every site $n$ of a Euclidean lattice and defines a finite-dimensional statistical integral

$$
Z_a=\int \prod_n d\phi_n\, e^{-S_a[\phi]}.
$$

For a real one-component scalar field on a hypercubic lattice, the standard nearest-neighbor action is

$$
S_a[\phi]
=a^d\sum_n\left[
\frac12\sum_\mu\left(\frac{\phi_{n+\hat\mu}-\phi_n}{a}\right)^2
+\frac12m_0^2\phi_n^2
+\frac{\lambda_0}{4!}\phi_n^4
\right].
$$

The free propagator is

$$
G_a(p)=\frac{1}{\widehat p^{\,2}+m_0^2},
\qquad
\widehat p^{\,2}=\frac4{a^2}\sum_\mu\sin^2\left(\frac{a p_\mu}{2}\right),
$$

so the continuum propagator is recovered at small $a p_\mu$. Interactions, however, make the real lesson sharper: the continuum theory is not obtained by merely writing a finite-difference action and then wishing $a$ away. One must tune bare couplings toward a critical point or critical surface so that the correlation length in lattice units diverges.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Scalar lattice field theory map: scalar variables on sites, nearest-neighbor finite differences, a lattice propagator in momentum space, and critical tuning toward a continuum limit.](/figures/nonperturbative-qft/lattice-scalar-action-propagator.svg)

<figcaption>

A scalar lattice theory has two complementary readings. At fixed nonzero $a$, it is a finite statistical system with fields on sites and nearest-neighbor couplings. Along a critical trajectory, $\xi/a\to\infty$, the same system can define a continuum scalar QFT or a universality class.

</figcaption>
</figure>

Scalar fields are the cleanest laboratory for lattice thinking. They show how locality, correlation length, criticality, finite volume, and continuum scaling work before gauge redundancy and fermion doubling enter the story.

## Prerequisites

Read [Euclidean Lattice](/nonperturbative-qft/lattice-field-theory/euclidean-lattice/), [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), and [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/). [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) is useful for understanding when Euclidean lattice correlators reconstruct a Hilbert-space spectrum.

## Core idea

A lattice scalar theory is an ordinary statistical system whose long-distance limit may become a continuum QFT. The lattice spacing cuts off short distances, the box cuts off long distances, and the action is chosen to be local and symmetry-compatible. The continuum limit is a scaling limit near criticality.

There are two equivalent mental pictures:

| Viewpoint | What the lattice theory is | What the continuum limit means |
|---|---|---|
| Regulator viewpoint | A cutoff version of a desired continuum scalar theory. | Remove the cutoff while holding physical observables fixed. |
| Statistical-mechanics viewpoint | A local model with variables on sites. | Approach a critical point where long-distance correlations become universal. |

The second viewpoint is often healthier. It prevents the common mistake of thinking the continuum theory is already present at nonzero lattice spacing.

## Setup and conventions

We work on a $d$-dimensional Euclidean hypercubic lattice with spacing $a$, sites $n\in\mathbb Z^d$ or $n_\mu=0,\ldots,N_\mu-1$, and physical lengths $L_\mu=N_\mu a$. Unless otherwise stated, use periodic boundary conditions.

A real scalar field assigns one real number to every site:

$$
\phi_n\in\mathbb R.
$$

The continuum integral and derivative are represented by

$$
\int d^d x\, f(x)\to a^d\sum_n f_n,
\qquad
\partial_\mu\phi(x_n)\to \frac{\phi_{n+\hat\mu}-\phi_n}{a}.
$$

The lattice Laplacian is

$$
-\Delta_a\phi_n
=\frac1{a^2}\sum_\mu\left(2\phi_n-\phi_{n+\hat\mu}-\phi_{n-\hat\mu}\right).
$$

The action is usually written in a continuum-looking normalization, as above, or in dimensionless lattice units. The two forms contain the same physics, but the dimensionless form is better for simulation and the continuum-looking form is better for orientation.

## The free scalar on a lattice

The free lattice scalar action is

$$
S_{0,a}[\phi]
=\frac12 a^d\sum_n\left[
\sum_\mu\left(\frac{\phi_{n+\hat\mu}-\phi_n}{a}\right)^2
+m_0^2\phi_n^2
\right].
$$

Using a finite periodic lattice, write

$$
\phi_n=\frac1{\sqrt V}\sum_p e^{i p\cdot a n}\,\widetilde\phi(p),
\qquad
V=\prod_\mu N_\mu,
$$

with momenta

$$
p_\mu=\frac{2\pi k_\mu}{L_\mu},
\qquad
-\frac\pi a<p_\mu\le \frac\pi a.
$$

The action diagonalizes as

$$
S_{0,a}=\frac12 a^d\sum_p
\left(\widehat p^{\,2}+m_0^2\right)\widetilde\phi(p)\widetilde\phi(-p),
$$

where

$$
\widehat p^{\,2}=\frac4{a^2}\sum_\mu\sin^2\left(\frac{a p_\mu}{2}\right).
$$

Thus the free two-point function is

$$
\langle \widetilde\phi(p)\widetilde\phi(q)\rangle
=\frac{1}{a^d}\frac{\delta_{p+q,0}}{\widehat p^{\,2}+m_0^2}
$$

up to the precise finite-volume Fourier normalization. The invariant lesson is not the bookkeeping factor; it is the kinetic operator

$$
K_a(p)=\widehat p^{\,2}+m_0^2.
$$

At small momenta,

$$
\widehat p^{\,2}=p^2-\frac{a^2}{12}\sum_\mu p_\mu^4+O(a^4p^6),
$$

so the leading continuum action is the usual Euclidean free scalar action, while the corrections are irrelevant lattice artifacts.

## Correlation length and the lattice mass

The lattice mass is the inverse correlation length measured in lattice units. For the free theory, the zero-spatial-momentum Euclidean time correlator decays as

$$
C(n_\tau)\sim e^{-aE\, n_\tau},
$$

where $E$ satisfies

$$
4\sinh^2\left(\frac{aE}{2}\right)=a^2m_0^2.
$$

Therefore

$$
aE=2\operatorname{arcsinh}\left(\frac{a m_0}{2}\right)
=am_0+O(a^3m_0^3).
$$

The physical continuum limit with a fixed nonzero mass requires

$$
am_{\rm phys}\to0,
\qquad
\xi_a\equiv \frac1{am_{\rm phys}}\to\infty.
$$

This is the core lattice slogan for scalar fields:

$$
\text{continuum QFT}\quad =\quad
\text{long-correlation-length limit of a local lattice model}.
$$

## Interacting scalar theory

The lattice $\phi^4$ theory is

$$
S_a[\phi]
=a^d\sum_n\left[
\frac12\sum_\mu(\nabla^+_\mu\phi_n)^2
+\frac12m_0^2\phi_n^2
+\frac{\lambda_0}{4!}\phi_n^4
\right].
$$

The bare mass $m_0^2$ is not the physical mass. In an interacting theory it receives cutoff-dependent additive renormalization. The critical point is located at some

$$
m_0^2=m_c^2(\lambda_0,a),
$$

or, in dimensionless variables, along a critical curve or critical surface in bare-coupling space.

Near a second-order transition, the correlation length behaves schematically as

$$
\xi_a\sim |t|^{-\nu},
\qquad
 t=\frac{m_0^2-m_c^2}{m_c^2}
$$

when $t$ is an appropriate reduced distance from criticality. The exponent $\nu$ and other long-distance data are universal within a universality class. The microscopic lattice action affects irrelevant corrections, not the leading continuum critical behavior.

In dimensions $d<4$, the Wilson–Fisher fixed point gives an interacting continuum scalar universality class. In $d=4$, the status of pure scalar $\phi^4$ as an interacting continuum theory is subtle: the standard expectation is triviality in the strict continuum limit, although scalar effective theories remain extremely useful below a cutoff.

## Ising and O(N) viewpoints

The one-component lattice scalar theory is closely related to the Ising universality class. One route is to take a strong local potential that favors

$$
\phi_n\approx \pm v.
$$

At long distances the details of the radial potential become unimportant, and the remaining low-energy variable behaves like an Ising spin. This is why the lattice $\phi^4$ model and the Ising model can describe the same critical continuum physics.

For an $N$-component scalar field,

$$
\boldsymbol\phi_n\in\mathbb R^N,
$$

one writes

$$
S_a[\boldsymbol\phi]
=a^d\sum_n\left[
\frac12\sum_\mu(\nabla^+_\mu\boldsymbol\phi_n)^2
+\frac12m_0^2\boldsymbol\phi_n^2
+\frac{\lambda_0}{4!}(\boldsymbol\phi_n^2)^2
\right],
$$

which has an $O(N)$ global symmetry. Depending on $d$ and the parameters, the long-distance physics may include symmetric massive phases, ordered phases, Goldstone modes, or critical fixed points.

:::caution[Finite volume]
At finite volume, an exact global symmetry is not spontaneously broken in the naive sense. To diagnose an ordered phase, use limits carefully: add a source or boundary condition, take the thermodynamic limit, and only then remove the source.
:::

## Continuum expansion and irrelevant operators

The lattice action has only the exact symmetries of the lattice, not full Euclidean rotations. Expanding the free kinetic term gives

$$
\widehat p^{\,2}=p^2-\frac{a^2}{12}\sum_\mu p_\mu^4+O(a^4p^6).
$$

In position space, the correction corresponds to higher-derivative operators such as

$$
a^2\sum_\mu(\partial_\mu^2\phi)^2.
$$

These terms are irrelevant near the continuum fixed point if the desired universality class is reached. Improved lattice actions add carefully chosen further-neighbor terms to cancel leading artifacts, replacing an $O(a^2)$ approach to the continuum by a faster one in suitable observables.

The lesson is not that the naive action is wrong. It is that every lattice action defines a point in the space of regularized theories. Universality says that many such points flow to the same long-distance continuum theory.

## Reflection positivity and transfer matrix

For a nearest-neighbor Euclidean scalar action with real positive weight, one can often construct a positive transfer matrix advancing the system by one Euclidean time step. This is the lattice version of Hilbert-space reconstruction.

A typical zero-momentum correlator has the form

$$
C(n_\tau)=\sum_{k} |\langle 0|\mathcal O|k\rangle|^2 e^{-aE_k n_\tau}.
$$

At large $n_\tau$, the lightest state with the quantum numbers of $\mathcal O$ dominates. This is the scalar-field prototype of the same spectral extraction used later for hadrons and glueballs.

The caveat is important: not every convenient discretization is reflection positive. A lattice action can be a useful regulator while making Hilbert-space positivity less direct at finite lattice spacing. The continuum limit may still be healthy, but spectral interpretation at finite $a$ then needs more care.

## Minimal workflow

For a scalar lattice theory, the conceptual workflow is:

1. choose a local lattice action and boundary conditions;
2. compute correlation functions at finite $a$ and finite volume;
3. extract correlation lengths, masses, susceptibilities, or Binder-type ratios;
4. vary the bare parameters to locate critical behavior or a physical scaling trajectory;
5. take large-volume and continuum limits with controlled errors.

The computational details depend on the method: exact enumeration in tiny systems, Gaussian integration for free theories, Monte Carlo for positive Euclidean weights, strong-coupling or hopping expansions, large-$N$ saddle points, or tensor methods.

## Common pitfalls

**Identifying $m_0$ with the measured mass.** The bare mass is a coupling in the cutoff theory. The measured mass comes from long-distance correlator decay and generally differs from $m_0$, especially in an interacting theory.

**Taking $a\to0$ without tuning.** A continuum limit requires a diverging correlation length in lattice units. Merely shrinking $a$ at fixed bare dimensionless couplings is not a complete continuum construction.

**Treating lattice artifacts as physical anisotropy.** Hypercubic lattices break continuous rotations at nonzero $a$. Rotational invariance should be checked as an emergent long-distance property.

**Forgetting finite-volume symmetry restoration.** In a finite box, tunneling between would-be broken vacua can restore the exact symmetry. Order parameters require the right source and volume limits.

**Assuming every scalar continuum limit is interacting.** In four dimensions, pure scalar $\phi^4$ theory is expected to be trivial in the strict continuum limit. As an effective theory below a cutoff, it is still a central and useful model.

## Relations to other pages

- [Euclidean Lattice](/nonperturbative-qft/lattice-field-theory/euclidean-lattice/) fixes the lattice geometry, momenta, finite differences, and spectral-extraction notation used here.
- [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) explains the RG reason that critical tuning is needed.
- [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/) gives the diagnostic language behind lattice masses and scaling windows.
- [Mass Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) explains why exponential Euclidean decay is spectral data.
- [Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) and [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) solve related scalar systems using saddle-point methods.
- [Lattice Gauge Fields](/nonperturbative-qft/lattice-field-theory/lattice-gauge-fields/) shows how the lattice changes when local gauge redundancy is present.

## Research status

Scalar lattice field theory is textbook-standard as a regulator, a statistical-mechanics model, and a source of continuum universality classes. The free theory is exactly solvable, and the interacting theory is a central example for RG, critical phenomena, and numerical methods.

The active questions are usually not about the existence of the lattice regulator itself. They concern precision continuum extrapolation, improved actions, critical exponents in difficult universality classes, scalar sectors coupled to gauge fields and fermions, finite-density or real-time extensions, and the strict continuum status of four-dimensional scalar theories.

## Exercises

### Exercise 1: Free lattice propagator

Starting from

$$
S_{0,a}=\frac12 a^d\sum_n\left[
\sum_\mu\left(\frac{\phi_{n+\hat\mu}-\phi_n}{a}\right)^2+m_0^2\phi_n^2\right],
$$

show that the momentum-space kinetic operator is $K_a(p)=\widehat p^{\,2}+m_0^2$.

<details>
<summary><strong>Solution</strong></summary>

Insert $\phi_n\propto e^{ip\cdot an}$. Then

$$
\phi_{n+\hat\mu}-\phi_n=(e^{ia p_\mu}-1)\phi_n.
$$

The quadratic finite-difference contribution gives

$$
\frac1{a^2}(e^{ia p_\mu}-1)(e^{-ia p_\mu}-1)
=\frac1{a^2}(2-e^{ia p_\mu}-e^{-ia p_\mu})
=\frac4{a^2}\sin^2\left(\frac{a p_\mu}{2}\right).
$$

Summing over $\mu$ and adding $m_0^2$ gives

$$
K_a(p)=\widehat p^{\,2}+m_0^2.
$$

</details>

### Exercise 2: Lattice energy of the free scalar

For zero spatial momentum, analytically continue the Euclidean momentum to $p_\tau=iE$ in the free lattice pole condition and show that

$$
4\sinh^2\left(\frac{aE}{2}\right)=a^2m_0^2.
$$

<details>
<summary><strong>Solution</strong></summary>

The denominator of the Euclidean propagator is

$$
\widehat p^{\,2}+m_0^2.
$$

At zero spatial momentum and $p_\tau=iE$,

$$
\frac4{a^2}\sin^2\left(\frac{i aE}{2}\right)+m_0^2
=-\frac4{a^2}\sinh^2\left(\frac{aE}{2}\right)+m_0^2.
$$

The pole condition gives

$$
-\frac4{a^2}\sinh^2\left(\frac{aE}{2}\right)+m_0^2=0,
$$

so

$$
4\sinh^2\left(\frac{aE}{2}\right)=a^2m_0^2.
$$

</details>

### Exercise 3: Why criticality is needed

Suppose a lattice scalar theory has measured correlation length $\xi_a=5$ in lattice units along a sequence of simulations. Can this sequence define a continuum limit with a nonzero physical correlation length as $a\to0$?

<details>
<summary><strong>Solution</strong></summary>

The physical correlation length is

$$
\xi_{\rm phys}=a\xi_a.
$$

If $\xi_a=5$ remains fixed while $a\to0$, then

$$
\xi_{\rm phys}\to0.
$$

This does not give a continuum QFT with finite long-distance physics. A continuum limit with fixed nonzero $\xi_{\rm phys}$ requires

$$
\xi_a\to\infty.
$$

</details>

### Exercise 4: Ising limit intuition

Explain why a scalar theory with a very steep double-well potential can have the same long-distance critical behavior as an Ising model.

<details>
<summary><strong>Solution</strong></summary>

A steep double-well potential forces each site variable to lie near one of two minima,

$$
\phi_n\approx \pm v.
$$

The low-energy site variable is then essentially a sign, just like an Ising spin. Near a second-order transition, long-distance behavior is controlled by symmetries, dimensionality, locality, and relevant operators, not by the microscopic shape of the potential. Thus the scalar lattice model and the Ising model can share the same universality class.

</details>

## References

### Standard first pass

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean scalar field integrals, lattice regularization, critical behavior, and continuum limits.
- J. B. Kogut, “An Introduction to Lattice Gauge Theory and Spin Systems,” for lattice spin systems, scalar/statistical analogies, and the bridge to gauge theory.
- M. Creutz, *Quarks, Gluons and Lattices*, for a physical introduction to lattice regularization and correlation-function extraction.

### Deeper references

- H. J. Rothe, *Lattice Gauge Theories*, for scalar and gauge lattice actions, continuum limits, and numerical foundations.
- I. Montvay and G. Münster, *Quantum Fields on a Lattice*, for systematic treatment of lattice field variables, actions, and simulations.
- M. Srednicki, *Quantum Field Theory*, for scalar path integrals, exact propagators, RG, and the introductory bridge to lattice theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for scalar path integrals, Wilsonian RG, and introductory lattice gauge context.

## Version history

- **2026-06-28:** Initial polished page on lattice scalar actions, propagators, correlation lengths, critical tuning, universality, finite-volume caveats, and continuum scaling.
