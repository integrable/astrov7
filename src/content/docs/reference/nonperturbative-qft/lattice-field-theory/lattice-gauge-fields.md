---
title: "Lattice Gauge Fields"
description: "Defines lattice gauge fields as group-valued link variables, explains their gauge transformations, plaquettes, Wilson loops, Haar measure, and continuum expansion."
sidebar:
  label: "Lattice Gauge Fields"
  order: 3
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut; Polyakov; Zinn-Justin; Srednicki; Schwartz; Rothe; Gattringer–Lang; Montvay–Münster; Altland–Simons."
topics:
  - lattice gauge theory
  - link variables
  - plaquettes
  - Wilson loops
  - Haar measure
  - gauge invariance
  - parallel transport
  - compact gauge fields
  - continuum limit
  - Yang–Mills theory
canonicalTopics:
  - nonperturbative-qft
  - lattice-field-theory
  - lattice-gauge-fields
  - link-variables
  - plaquettes
  - wilson-loops
  - gauge-invariance
researchStatus:
  established:
    - "Group-valued link variables and plaquette loops are the standard gauge-invariant lattice formulation of compact gauge fields."
  active:
    - "Chiral gauge theories, improved gauge actions, topology at fine lattice spacing, real-time gauge dynamics, and finite-density gauge theories require additional specialized methods."
---

## Summary

A **lattice gauge field** is not a vector $A_\mu(n)$ placed on a site. It is a group element on an oriented link,

$$
U_\mu(n)\in G,
$$

interpreted as parallel transport from $n$ to $n+\hat\mu$. Under a site-dependent gauge transformation $g(n)\in G$,

$$
U_\mu(n)\to g(n)U_\mu(n)g(n+\hat\mu)^{-1}.
$$

This single formula is the reason lattice gauge theory can be defined with exact gauge invariance at finite lattice spacing, before any continuum limit is taken.

The elementary gauge-invariant local object is the plaquette,

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\hat\mu)
U_\mu(n+\hat\nu)^{-1}U_\nu(n)^{-1},
$$

whose trace is invariant. In the smooth-field limit,

$$
U_{\mu\nu}(n)=\exp\left(i a^2 g F_{\mu\nu}(x_n)+O(a^3)\right),
$$

so plaquettes are the lattice version of curvature.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Lattice gauge-field dictionary: a link variable transforms at its endpoints, a plaquette is an elementary closed transporter, and traces of closed loops are gauge invariant.](/figures/nonperturbative-qft/lattice-gauge-link-plaquette.svg)

<figcaption>

Lattice gauge fields are group-valued parallel transporters. Open links transform at their endpoints, so they are not gauge-invariant observables by themselves. Closed products, such as plaquettes and Wilson loops, transform by conjugation at the base point; their traces are gauge invariant.

</figcaption>
</figure>

Gauge fields therefore enter the lattice through geometry, not through a naive finite difference of $A_\mu$. The lattice variable knows from the start that gauge theory is about parallel transport, holonomy, and curvature.

## Prerequisites

Read [Euclidean Lattice](/nonperturbative-qft/lattice-field-theory/euclidean-lattice/) and [Lattice Scalar Field Theory](/nonperturbative-qft/lattice-field-theory/lattice-scalar-field-theory/) first. For physical diagnostics, it helps to know [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), [Center Symmetry](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/), and [One-Form Symmetry and Confinement](/nonperturbative-qft/confinement-screening-mass-gap/one-form-symmetry-confinement/).

## Core idea

Continuum gauge theory compares fields at nearby points using a connection. On the lattice, nearby points are genuinely separate, so the connection should be represented by the finite parallel transporter between them. That finite transporter is the link variable.

The construction is a dictionary:

| Continuum idea | Lattice object |
|---|---|
| point $x$ | site $n$ |
| gauge transformation $g(x)$ | site variable $g(n)$ |
| connection $A_\mu(x)$ | link transporter $U_\mu(n)$ |
| covariant derivative | gauge-covariant finite difference |
| curvature $F_{\mu\nu}$ | plaquette holonomy $U_{\mu\nu}(n)$ |
| Wilson line | ordered product of links along a path |
| Yang–Mills action | local sum over plaquettes and larger loops |

The lattice does not break gauge invariance because gauge invariance is implemented exactly by group multiplication.

## Setup and conventions

Let $G$ be a compact gauge group, such as $U(1)$, $SU(N)$, or a finite group. We work on a $d$-dimensional Euclidean hypercubic lattice with spacing $a$. A positively oriented link from $n$ to $n+\hat\mu$ carries

$$
U_\mu(n)\in G.
$$

The oppositely oriented link carries the inverse group element. A convenient convention is

$$
U_{-\mu}(n)=U_\mu(n-\hat\mu)^{-1},
$$

which is the link from $n$ to $n-\hat\mu$.

For a smooth continuum gauge field in the fundamental representation, a link variable is approximated by

$$
U_\mu(n)
\approx \mathcal P\exp\left(i g\int_{x_n}^{x_n+a\hat\mu} dx^\mu A_\mu(x)\right)
\approx \exp\left(iag A_\mu(x_n+a\hat\mu/2)\right).
$$

Here $g$ is the continuum gauge coupling. Some lattice conventions absorb $g$ into $A_\mu$ or use anti-Hermitian generators. The transformation law and closed-loop observables are convention-independent.

## Gauge transformations on the lattice

A gauge transformation assigns a group element to each site:

$$
g(n)\in G.
$$

For matter fields in a representation $R$,

$$
\psi_n\to R(g(n))\psi_n.
$$

A link transforms as

$$
U_\mu(n)
\to g(n)U_\mu(n)g(n+\hat\mu)^{-1}
$$

in the representation where the link is written. This is exactly what a parallel transporter should do: it maps a vector at $n+\hat\mu$ back to a vector at $n$, so it must transform with one group action at each endpoint.

A nearest-neighbor gauge-covariant difference for a fundamental scalar or fermion is

$$
D_\mu^+\psi_n
=\frac{U_\mu(n)\psi_{n+\hat\mu}-\psi_n}{a}.
$$

It transforms covariantly:

$$
D_\mu^+\psi_n\to g(n)D_\mu^+\psi_n.
$$

This is the lattice replacement for a continuum covariant derivative.

## Plaquettes as curvature

The elementary closed loop on a hypercubic lattice is the plaquette. Starting at $n$, going along $\mu$, then $\nu$, then backward along $\mu$, then backward along $\nu$, define

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\hat\mu)
U_\mu(n+\hat\nu)^{-1}U_\nu(n)^{-1}.
$$

Under a gauge transformation,

$$
U_{\mu\nu}(n)\to g(n)U_{\mu\nu}(n)g(n)^{-1}.
$$

Therefore

$$
\operatorname{tr} U_{\mu\nu}(n)
$$

is gauge invariant. More generally, the trace of the ordered product of link variables around any closed loop is gauge invariant.

In the continuum limit, the plaquette measures curvature. For smooth fields,

$$
U_{\mu\nu}(n)
=\exp\left(i a^2 g F_{\mu\nu}(x_n)+O(a^3)\right).
$$

For $G=U(1)$, this statement is especially transparent. Write

$$
U_\mu(n)=e^{i\theta_\mu(n)}.
$$

Then

$$
U_{\mu\nu}(n)=e^{i\theta_{\mu\nu}(n)},
$$

where

$$
\theta_{\mu\nu}(n)
=\theta_\mu(n)+\theta_\nu(n+\hat\mu)-\theta_\mu(n+\hat\nu)-\theta_\nu(n).
$$

This is the lattice curl of the compact gauge angle.

## The gauge-field path integral

For compact $G$, the lattice gauge-field partition function has the schematic form

$$
Z=\int \prod_{n,\mu} dU_\mu(n)\, e^{-S[U]},
$$

where $dU$ is the normalized Haar measure on $G$. The Haar measure is invariant under left and right multiplication,

$$
dU=d(gU)=d(Ug),
$$

so the product measure is gauge invariant.

A pure gauge action is built from traces of closed loops. The simplest local action is the Wilson plaquette action. For $SU(N)$, one common normalization is

$$
S_W[U]=\frac{\beta}{N}\sum_{n}\sum_{\mu<\nu}
\operatorname{Re}\operatorname{tr}\left(1-U_{\mu\nu}(n)\right),
\qquad
\beta=\frac{2N}{g_0^2}.
$$

The detailed normalization belongs to the Wilson Action page. The essential point here is structural: locality plus gauge invariance naturally leads to closed loops, and the smallest closed loop is the plaquette.

## Wilson lines and Wilson loops

For an oriented path $C$ made of links $\ell_1,\ell_2,\ldots,\ell_m$, define the parallel transporter

$$
U(C)=U(\ell_1)U(\ell_2)\cdots U(\ell_m),
$$

with inverses used for negatively oriented links. If $C$ begins at $n_i$ and ends at $n_f$, then

$$
U(C)\to g(n_i)U(C)g(n_f)^{-1}.
$$

Thus an open Wilson line is not gauge invariant by itself. It becomes gauge invariant only when its endpoints are attached to matter fields or boundary data.

For a closed loop $C$ based at $n$, the transporter transforms by conjugation:

$$
U(C)\to g(n)U(C)g(n)^{-1}.
$$

Therefore the Wilson loop

$$
W_R(C)=\operatorname{tr}_R U(C)
$$

is gauge invariant. Large Wilson loops diagnose confinement, screening, Coulomb behavior, and one-form symmetry realization depending on the theory and matter content.

## Compactness matters

Lattice gauge theory usually uses compact group-valued variables. This is not a harmless detail. For $U(1)$, compact and noncompact formulations can have different nonperturbative sectors.

In compact $U(1)$ lattice gauge theory,

$$
U_\mu(n)=e^{i\theta_\mu(n)},
\qquad \theta_\mu\sim \theta_\mu+2\pi.
$$

The periodicity allows topological defects such as lattice monopoles in suitable dimensions. This compactness is central to Polyakov’s mechanism for confinement in compact QED in three dimensions. A noncompact formulation with $A_\mu\in\mathbb R$ keeps perturbative photons but can miss these sectors.

The moral is familiar from nonperturbative QFT: two formulations with the same weak-field expansion can differ globally.

## Continuum expansion of the plaquette action

For a smooth $SU(N)$ gauge field with Hermitian generators normalized by

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

write

$$
F_{\mu\nu}=F_{\mu\nu}^aT^a.
$$

Using

$$
U_{\mu\nu}=\exp(i a^2 g_0 F_{\mu\nu}+O(a^3)),
$$

one finds

$$
\operatorname{Re}\operatorname{tr}(1-U_{\mu\nu})
=\frac{a^4 g_0^2}{2}\operatorname{tr}F_{\mu\nu}^2+O(a^6)
=\frac{a^4 g_0^2}{4}F_{\mu\nu}^aF_{\mu\nu}^a+O(a^6).
$$

With $\beta=2N/g_0^2$, the Wilson action approaches the continuum Yang–Mills action in four dimensions,

$$
S_W\to \frac14\int d^4x\,F_{\mu\nu}^aF_{\mu\nu}^a,
$$

up to the chosen convention for where the gauge coupling is placed. The continuum expansion is a check, not the whole definition. The nonperturbative definition is the compact group integral over all link variables.

## Gauge fixing is optional, not foundational

For gauge-invariant observables, lattice gauge theory does not require gauge fixing. The finite-dimensional integral over compact links is well-defined, and gauge-variant expectation values vanish or are undefined as physical observables.

This is conceptually important. In continuum perturbation theory, gauge fixing is introduced to define propagators and Feynman rules. On the lattice, Wilson loops, plaquettes, Polyakov loops, and gauge-invariant matter correlators can be defined directly.

Gauge fixing is still used on the lattice for gauge-dependent diagnostics, propagator studies, and matching to continuum schemes. But it is not the starting point of the nonperturbative definition.

## Common pitfalls

**Putting $A_\mu$ on links but transforming it like a site field.** The finite-a gauge field is the transporter $U_\mu(n)$, not an additive vector. Its transformation involves both endpoints of the link.

**Calling an open Wilson line an observable without endpoints.** An open line transforms at its two ends. It becomes gauge invariant only after contracting the endpoints with matter fields, boundary states, or other charged insertions.

**Forgetting orientation.** Reversing a link replaces $U$ by $U^{-1}$, or by $U^\dagger$ for unitary groups. Many sign and order mistakes in lattice gauge theory are orientation mistakes in disguise.

**Thinking the plaquette is only a discretized $F_{\mu\nu}^2$.** Perturbatively, its expansion gives curvature. Nonperturbatively, the plaquette is a compact holonomy and knows about large field configurations that no small-$A_\mu$ expansion sees.

**Assuming exact gauge invariance implies exact continuum spacetime symmetry.** Gauge invariance is exact at nonzero $a$. Continuous rotations and translations are not; they must re-emerge in the scaling limit.

## Relations to other pages

- [Euclidean Lattice](/nonperturbative-qft/lattice-field-theory/euclidean-lattice/) introduces sites, links, plaquettes, finite volume, and the Brillouin zone.
- [Lattice Scalar Field Theory](/nonperturbative-qft/lattice-field-theory/lattice-scalar-field-theory/) gives the scalar-site-variable version before gauge redundancy enters.
- [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) uses closed link products to define a confinement diagnostic.
- [String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/) explains how large Wilson loops extract the energy per unit length of a flux tube.
- [Center Symmetry](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/) and [One-Form Symmetry and Confinement](/nonperturbative-qft/confinement-screening-mass-gap/one-form-symmetry-confinement/) explain the symmetry meaning of genuine loop operators.
- [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) shows why compact lattice gauge variables can have nonperturbative monopole sectors.

## Research status

The link-variable formulation of compact lattice gauge theory is established. It is the standard nonperturbative regulator for pure Yang–Mills theory and vectorlike gauge theories such as QCD, and it is the language in which Wilson loops, Polyakov loops, plaquette actions, and lattice gauge simulations are defined.

Active work concerns the hard edges: chiral gauge theories, topological sectors at fine lattice spacing, improved gauge actions, real-time dynamics, finite-density gauge theories, quantum simulation, and precise matching between lattice observables and continuum schemes. The basic link-and-plaquette construction is not in doubt; the difficult questions lie in limits, algorithms, and theories whose Euclidean weights or chiral structure are delicate.

## Exercises

### Exercise 1: Gauge covariance of the lattice derivative

Let $\psi_n\to g(n)\psi_n$ and

$$
D_\mu^+\psi_n=\frac{U_\mu(n)\psi_{n+\hat\mu}-\psi_n}{a}.
$$

Show that $D_\mu^+\psi_n\to g(n)D_\mu^+\psi_n$.

<details>
<summary><strong>Solution</strong></summary>

Under a gauge transformation,

$$
U_\mu(n)\psi_{n+\hat\mu}
\to g(n)U_\mu(n)g(n+\hat\mu)^{-1}g(n+\hat\mu)\psi_{n+\hat\mu}.
$$

The two endpoint factors at $n+\hat\mu$ cancel, leaving

$$
U_\mu(n)\psi_{n+\hat\mu}
\to g(n)U_\mu(n)\psi_{n+\hat\mu}.
$$

Also $\psi_n\to g(n)\psi_n$. Therefore

$$
D_\mu^+\psi_n
\to \frac{g(n)U_\mu(n)\psi_{n+\hat\mu}-g(n)\psi_n}{a}
=g(n)D_\mu^+\psi_n.
$$

</details>

### Exercise 2: Plaquette transformation law

Using

$$
U_\mu(n)\to g(n)U_\mu(n)g(n+\hat\mu)^{-1},
$$

show that

$$
U_{\mu\nu}(n)
\to g(n)U_{\mu\nu}(n)g(n)^{-1}.
$$

<details>
<summary><strong>Solution</strong></summary>

Transform each factor in

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\hat\mu)
U_\mu(n+\hat\nu)^{-1}U_\nu(n)^{-1}.
$$

The site factors at the intermediate corners cancel pairwise. Only the group element at the base point remains on the left and right:

$$
U_{\mu\nu}(n)
\to g(n)U_{\mu\nu}(n)g(n)^{-1}.
$$

Thus $\operatorname{tr}U_{\mu\nu}(n)$ is gauge invariant.

</details>

### Exercise 3: Abelian plaquette angle

For compact $U(1)$, take $U_\mu(n)=e^{i\theta_\mu(n)}$. Derive the plaquette angle

$$
\theta_{\mu\nu}(n)
=\theta_\mu(n)+\theta_\nu(n+\hat\mu)-\theta_\mu(n+\hat\nu)-\theta_\nu(n).
$$

<details>
<summary><strong>Solution</strong></summary>

The plaquette is

$$
U_{\mu\nu}(n)
=U_\mu(n)U_\nu(n+\hat\mu)
U_\mu(n+\hat\nu)^{-1}U_\nu(n)^{-1}.
$$

For $U(1)$, multiplication is ordinary addition of phases, while inversion changes the sign of the phase. Hence

$$
U_{\mu\nu}(n)
=\exp i\left[\theta_\mu(n)+\theta_\nu(n+\hat\mu)-\theta_\mu(n+\hat\nu)-\theta_\nu(n)\right].
$$

This gives the stated lattice curl.

</details>

### Exercise 4: Why closed loops are special

Explain why the trace of a closed Wilson loop is gauge invariant, while the trace of a generic open transporter is not even well-defined as a gauge-invariant observable.

<details>
<summary><strong>Solution</strong></summary>

An open transporter from $n_i$ to $n_f$ transforms as

$$
U(C)\to g(n_i)U(C)g(n_f)^{-1}.
$$

Since the left and right transformations live at different sites, taking a trace does not cancel them. For a closed loop, $n_i=n_f=n$, so

$$
U(C)\to g(n)U(C)g(n)^{-1}.
$$

The trace is invariant under conjugation:

$$
\operatorname{tr}[gUg^{-1}]=\operatorname{tr}U.
$$

Therefore closed traced Wilson loops are gauge invariant.

</details>

## References

### Standard first pass

- J. B. Kogut, “An Introduction to Lattice Gauge Theory and Spin Systems,” for link variables, plaquettes, Wilson loops, transfer matrices, and confinement diagnostics.
- M. Creutz, *Quarks, Gluons and Lattices*, for a classic physical introduction to lattice gauge theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the lattice-gauge-theory discussion in Yang–Mills theory.

### Deeper references

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean field integrals, lattice regularization, link variables, and plaquette actions.
- H. J. Rothe, *Lattice Gauge Theories*, for systematic treatment of compact lattice gauge theory and the Wilson action.
- I. Montvay and G. Münster, *Quantum Fields on a Lattice*, for gauge fields, fermions, and simulation methods.
- C. Gattringer and C. B. Lang, *Quantum Chromodynamics on the Lattice*, for QCD-focused lattice gauge theory.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for link variables, plaquette actions, Wilson loops, and the condensed-matter gauge-theory perspective.
- A. M. Polyakov, *Gauge Fields and Strings*, for compact gauge fields, strong-coupling ideas, and nonperturbative gauge dynamics.

## Version history

- **2026-06-28:** Initial polished page defining link variables, gauge transformations, plaquettes, Haar measure, Wilson loops, compactness, continuum expansion, and common pitfalls.
