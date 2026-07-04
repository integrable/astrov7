---
title: "Beyond Perturbation Theory"
description: "A conceptual and technical guide to what perturbation theory computes, what it misses, and why nonperturbative QFT is not just strong coupling."
sidebar:
  label: "Beyond Perturbation Theory"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman; Polyakov; Mariño; Shifman; Wilson–Kogut; Zinn-Justin."
topics:
  - perturbation theory
  - asymptotic expansions
  - semiclassical saddles
  - nonperturbative scales
  - confinement
  - lattice definitions
canonicalTopics:
  - nonperturbative-qft
  - asymptotic-series
  - instantons
  - confinement
  - wilsonian-rg
  - lattice-field-theory
researchStatus:
  established:
    - "Perturbative expansions in QFT are usually formal asymptotic expansions around a chosen saddle or fixed point, and many physical effects are invisible in any finite order of that expansion."
  active:
    - "The precise reconstruction of full nonperturbative answers from perturbative data, especially in realistic four-dimensional QFTs, is an active research area involving resurgence, lattice methods, Hamiltonian methods, bootstrap ideas, and dualities."
---

## Summary

Perturbation theory is the expansion of a QFT around a chosen solvable starting point: a free theory, a classical saddle, a weakly coupled fixed point, or a large-N saddle. It is one of the great technologies of physics. It gives Feynman diagrams, loop expansions, anomalous dimensions, scattering amplitudes, effective actions, beta functions, and precision tests.

But perturbation theory is not the whole theory. A perturbative expansion around $g=0$ has the schematic form

$$
\mathcal O(g)\sim \sum_{n=0}^{\infty}a_n g^n,
$$

while many physical effects scale like

$$
e^{-A/g^2},
\qquad
e^{-A/g},
\qquad
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right],
$$

or are tied to distinct topological sectors, degenerate vacua, confinement, mass gaps, strong-coupling phases, or extended operators. Such effects are invisible in ordinary Taylor expansion at $g=0$.

Nonperturbative QFT is the study of the full quantum theory beyond this local expansion. It includes semiclassical saddles such as instantons and solitons, lattice definitions and continuum limits, order parameters and disorder operators, confinement and screening, large-N saddle points, functional equations, exact low-dimensional models, tensor-network and Hamiltonian methods, and the modern idea that perturbative and nonperturbative sectors may be linked by resurgence.

The key slogan is:

$$
\text{perturbation theory is local data; nonperturbative QFT asks for the global object.}
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![Perturbation theory as a local chart on theory space](/figures/nonperturbative-qft/perturbation-theory-local-chart.svg)

<figcaption>

Perturbation theory is a local chart near a chosen saddle or fixed point. Nonperturbative physics includes other saddles, topological sectors, phase boundaries, gaps, confinement, and observables that are not determined by a Taylor series around one point.

</figcaption>
</figure>

## Prerequisites

You should know the basic path-integral expansion around a Gaussian integral, the meaning of a Feynman diagram expansion, and the idea of renormalization. The conventions used below are fixed in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

This page is a conceptual first pass. Later pages turn the slogans into calculations.

## Core idea

A perturbative calculation starts by choosing a simple anchor. In a scalar theory, the anchor might be the free action

$$
S_0[\phi]=\int d^dx\left[\frac12(\partial\phi)^2+\frac12m^2\phi^2\right]
$$

and treating an interaction such as

$$
S_{\mathrm{int}}[\phi]=\int d^dx\,\frac{\lambda}{4!}\phi^4
$$

as small. In a gauge theory, the anchor might be the weak-coupling expansion around $A_\mu=0$. In a semiclassical problem, the anchor might be a classical solution. In a large-N problem, the anchor might be a saddle point of an auxiliary-field or eigenvalue integral.

This anchor gives a coordinate system near one point in theory space. It is powerful precisely because it is local: small fluctuations are tractable, Gaussian integrals can be evaluated, Wick contractions become diagrams, and renormalization organizes ultraviolet sensitivity.

The weakness is the same as the strength. A local coordinate chart need not see the global topology of the space. It need not know that the potential has another minimum, that gauge fields have disconnected topological sectors, that the true spectrum has no colored particles, that the large-distance theory has a mass gap, or that a symmetry has been realized in a way no weakly coupled elementary field makes obvious.

So “nonperturbative” does not mean “we dislike Feynman diagrams.” It means that the question being asked is not answered by the ordinary expansion around one weakly coupled saddle.

## Setup and conventions

Most of this page uses a Euclidean path integral

$$
Z(g)=\int\mathcal D\Phi\,e^{-S_E[\Phi;g]}.
$$

A perturbative expansion usually comes from splitting

$$
S_E=S_0+gS_1
$$

or, in a semiclassical normalization,

$$
S_E=\frac{1}{g^2}S_{\mathrm{cl}}.
$$

These two forms lead to different-looking powers, but the same conceptual issue: the expansion is built around selected configurations and selected variables.

A statement is called perturbative when it is determined order by order in such an expansion. A statement is called nonperturbative when it requires information that is not captured by all finite orders of that expansion, or when the very definition of the theory requires a regulator, Hilbert-space construction, lattice limit, exact solution, or other method not reducible to formal expansion around a Gaussian theory.

The words “weak coupling” and “strong coupling” are useful but not identical to “perturbative” and “nonperturbative.” This distinction is so important that it deserves to be said early: instanton effects can be sharply controlled at weak coupling and still be nonperturbative.

## What perturbation theory computes

Perturbation theory computes fluctuations around a chosen starting point. In the simplest path-integral version,

$$
Z[J]=\int\mathcal D\phi\,\exp\left[-S_0[\phi]-gS_{\mathrm{int}}[\phi]+\int J\phi\right]
$$

is expanded as

$$
Z[J]=\sum_{n=0}^{\infty}\frac{(-g)^n}{n!}\int\mathcal D\phi\,S_{\mathrm{int}}[\phi]^n
\exp\left[-S_0[\phi]+\int J\phi\right].
$$

The Gaussian measure defined by $S_0$ reduces the coefficients to Wick contractions. The resulting diagrams can be spectacularly useful. They compute scattering amplitudes, beta functions, anomalous dimensions, effective potentials, Wilson coefficients, short-distance operator products, and response functions.

Perturbation theory is especially natural when there is a small dimensionless parameter at the scale of interest. In QED this parameter is the fine-structure constant. In asymptotically free gauge theories it is the running coupling at short distances. In effective field theory it may be a ratio such as $E/M$. In statistical field theory near four dimensions it may be $\epsilon=4-d$. In large-N expansions it may be $1/N$.

Perturbation theory is also local in field space. It assumes that the relevant configurations are small fluctuations around the chosen saddle. Around a stable minimum $\phi_0$, a scalar action begins as

$$
S_E[\phi_0+\eta]
=S_E[\phi_0]+\frac12\int\eta K\eta+\text{interactions in }\eta.
$$

The quadratic operator $K$ gives the propagator; the higher terms give vertices. This is not merely a computational trick. It is the mathematical reason why perturbation theory knows about small oscillations, quasiparticles, and local response.

## The first obstruction: asymptotic series

A convergent power series defines a function inside its radius of convergence. Perturbation series in QFT usually do something weaker. They often define an asymptotic expansion:

$$
\mathcal O(g)-\sum_{n=0}^{N-1}a_ng^n=o(g^{N-1})
\qquad g\to0
$$

for each fixed $N$, without converging as $N\to\infty$.

This is not a small technical defect. It is a structural warning. The coefficients $a_n$ in quantum mechanics and QFT often grow factorially,

$$
a_n\sim C\,A^{-n}\,n!,
$$

or with related factorial behavior. Then the best approximation at small $g$ is obtained by stopping the series near its least term, not by summing forever.

A quick way to feel the issue is to remember Dyson’s argument for QED: if the perturbative series in the electric charge had a nonzero radius of convergence around $e=0$, one could analytically continue to negative $e^2$, where like charges attract and the vacuum is catastrophically unstable. The argument is not a proof of every modern statement about every QFT series, but it captures the reason one should not expect ordinary perturbation theory to be a convergent definition of the theory.

The asymptotic nature of perturbation theory does not make it useless. Quite the opposite: asymptotic series are often incredibly accurate when truncated intelligently. The point is that their accuracy is local and limited. After the least term, the remainder is typically of the same order as nonperturbative effects.

## The second obstruction: functions with zero perturbative expansion

The function

$$
f(g)=e^{-A/g^2},
\qquad A>0,
$$

for $g>0$ has a dramatic property:

$$
\left.\frac{d^n}{dg^n}e^{-A/g^2}\right|_{g=0}=0
$$

for every nonnegative integer $n$, if the function is extended smoothly by setting $f(0)=0$.

Therefore its Taylor series at $g=0$ is identically zero, even though $f(g)$ is not zero for any positive $g$. Ordinary perturbation theory cannot see this term. No one-loop, ten-loop, or million-loop calculation will produce it as a finite-order contribution.

This is the basic mathematical shape of many semiclassical nonperturbative effects. In Yang–Mills theory, a unit instanton contributes with action

$$
S_{\mathrm{inst}}=\frac{8\pi^2}{g^2},
$$

so its semiclassical weight contains

$$
e^{-8\pi^2/g^2}.
$$

In quantum mechanics, tunneling through a barrier often contributes

$$
e^{-S_0/\hbar}.
$$

If $\hbar$ is the expansion parameter, tunneling is nonperturbative in $\hbar$. The effect can be tiny and exquisitely controlled, but it is still invisible to ordinary perturbation theory around one minimum.

:::note[Nonperturbative does not mean numerically large]
An effect can be nonperturbative and very small. Instantons at weak coupling are the standard example. The word describes how the effect appears in an expansion, not whether it dominates numerically.
:::

## The third obstruction: the wrong saddle

Perturbation theory answers questions near the saddle you choose. But the path integral may receive contributions from several saddles:

$$
Z\sim \sum_{\alpha}e^{-S_E[\Phi_\alpha]}Z_\alpha^{\mathrm{fluct}}.
$$

The label $\alpha$ may distinguish classical solutions, topological sectors, degenerate vacua, boundary conditions, flux sectors, or complex saddles after analytic continuation. Expanding around only one saddle may give a perfectly correct local expansion and still miss the physics of the full sum.

The double-well potential in quantum mechanics is the friendly warning sign. Perturbation theory around the left minimum gives a formal oscillator series. Perturbation theory around the right minimum gives the same local series. The true low-energy eigenstates, however, are symmetric and antisymmetric combinations split by tunneling. The splitting is exponentially small in the semiclassical limit:

$$
\Delta E\sim e^{-S_{\mathrm{inst}}/\hbar}.
$$

No perturbative calculation around one well produces that splitting. The missing fact is not a complicated Feynman diagram. It is the existence of another well and paths connecting the two wells in Euclidean time.

Gauge theory has a richer version. In four-dimensional Yang–Mills theory, finite-action Euclidean gauge fields are organized by an integer topological charge $Q$. The theta-dependent partition function has the schematic form

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

Perturbation theory around the trivial sector $Q=0$ does not reconstruct the full theta dependence. The missing data are global data about the gauge-field configuration space.

## The fourth obstruction: changing the degrees of freedom

Perturbation theory often starts with fields appearing in a Lagrangian. But the physical long-distance degrees of freedom need not look like those fields.

In QCD, the microscopic Lagrangian uses quark and gluon fields. At short distances, asymptotic freedom makes perturbative quarks and gluons the right variables for many inclusive processes. At long distances, the observed spectrum consists of hadrons, and isolated colored states are absent. The question “why do colored particles not appear as asymptotic states?” is not a high-order correction to a quark scattering amplitude. It is a question about confinement, the mass gap, Wilson loops, center symmetry, screening, and the global structure of the theory.

Condensed matter supplies the same lesson in a different accent. The microscopic variables may be electrons and ions, but the long-distance theory may use phonons, magnons, vortices, Cooper pairs, anyons, gauge fields, or order-parameter fields. The emergence of the right variables is itself a nonperturbative phenomenon when it requires reorganizing the Hilbert space or changing the vacuum.

A useful rule of thumb:

$$
\text{if the correct low-energy excitations are not small fluctuations of the fields you expanded in, perturbation theory is probably not the right language.}
$$

## The fifth obstruction: phases and order parameters

A phase of QFT is not just a value of a coupling. It is a pattern of long-distance behavior. It may be characterized by a mass gap, spontaneous symmetry breaking, topological order, confinement, deconfinement, conformal behavior, Goldstone modes, long-range entanglement, or boundary degrees of freedom.

Perturbation theory can describe some phases very well. For example, a weakly coupled Higgs phase may have an excellent expansion around a classical vacuum. Chiral perturbation theory describes pions by expanding around a symmetry-breaking pattern. Perturbative RG can diagnose fixed points near four dimensions or weak Banks–Zaks fixed points.

But the existence of a phase, the transition between phases, and the correct diagnostic are often nonperturbative questions. Examples include:

| Phenomenon | Why ordinary perturbation theory is not enough |
|---|---|
| Spontaneous symmetry breaking | At finite volume the exact ground state may preserve the symmetry; the order parameter requires an infinite-volume limit and often a source. |
| Confinement | The statement concerns the spectrum and large Wilson loops, not a finite number of gluon diagrams. |
| Mass gap | A gap is a global spectral property. Perturbation theory around massless fields may not generate it at any finite order. |
| Topological sectors | Different sectors may be disconnected in configuration space and summed with theta angles or background fields. |
| Disorder operators | The diagnostic may be a defect or boundary-condition-changing operator, not a local polynomial in elementary fields. |
| Dual phases | The weakly coupled variables in one description may be strongly coupled or nonlocal in another. |

This is why nonperturbative QFT spends so much time on observables. If the observable is poorly chosen, the phenomenon can look mysterious or even nonexistent.

## Running coupling and dimensional transmutation

Asymptotically free theories show one of the cleanest ways perturbation theory points beyond itself. Suppose the beta function begins as

$$
\mu\frac{dg}{d\mu}=-b_0g^3+O(g^5),
\qquad b_0>0.
$$

Solving the one-loop equation gives

$$
\frac{1}{g^2(\mu)}=2b_0\log\frac{\mu}{\Lambda},
$$

or equivalently

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

The scale $\Lambda$ is generated from a dimensionless coupling and a renormalization scale. This is dimensional transmutation.

The crucial point is that $\Lambda$ is nonanalytic at $g=0$. No finite-order expansion in $g^2(\mu)$ produces it. Yet in an asymptotically free confining theory, masses are expected to be proportional to this scale:

$$
m_{\mathrm{gap}}\sim C\Lambda,
$$

with a dimensionless constant $C$ determined by the full theory. Perturbation theory can tell us how $g$ runs at short distances and can define $\Lambda$ in a chosen scheme. It does not, by itself, compute the hadron spectrum or prove confinement.

This is a good example of a mature attitude: perturbation theory is not wrong. It gives indispensable ultraviolet information. It simply does not close the infrared problem.

## Nonperturbative does not mean one method

There is no single “nonperturbative method.” The subject is a toolkit, and each tool has a domain of control.

| Method or viewpoint | Small or organizing parameter | What it can reveal | Main caveat |
|---|---|---|---|
| Semiclassical saddles | $g^2$, $\hbar$, barrier action | Tunneling, instantons, solitons, false-vacuum decay, theta dependence | Requires controlled saddles and fluctuation determinants. |
| Lattice field theory | lattice spacing $a$, volume, statistics | Nonperturbative definition, spectra, string tensions, thermodynamics | Continuum extrapolation and sign/chiral/real-time problems can be hard. |
| Large-N expansion | $1/N$ | Factorization, planar dominance, master fields, matrix models, solvable sectors | $N=3$ may not be close enough; some effects are $e^{-N}$. |
| Strong-coupling expansion | inverse coupling or hopping parameters | Area laws, lattice phases, qualitative confinement mechanisms | May not connect analytically to the continuum limit. |
| Schwinger–Dyson equations | hierarchy plus truncation | Relations among exact correlators, dynamical mass generation | Infinite hierarchy; truncations need control. |
| Hamiltonian and tensor methods | finite basis, bond dimension, volume | Spectra, real-time evolution, low-dimensional models | Continuum and high-dimensional limits are difficult. |
| Exact low-dimensional methods | integrability, bosonization, CFT data | Exact spectra, S-matrices, correlation functions, dualities | Special theories; lessons may not generalize directly. |
| Symmetry and topology | global constraints | Anomaly matching, order/disorder diagnostics, selection rules | Often constrains rather than computes numbers. |
| Resurgence and transseries | coupled perturbative and exponential sectors | Large-order behavior and nonperturbative ambiguities | Complete control in realistic QFTs is still limited. |

A good nonperturbative argument says what controls it. A lattice result may be controlled by continuum and volume extrapolations. A semiclassical result may be controlled by weak coupling and isolated saddles. A large-N result may be controlled by $1/N$. A symmetry argument may be exact but only constraining.

## Semiclassical versus strongly coupled

A common mistake is to equate nonperturbative with strongly coupled. The relation is more subtle.

A semiclassical instanton calculation can be weakly coupled. The saddle action is large,

$$
S_{\mathrm{inst}}\sim \frac{1}{g^2},
$$

so the contribution is small but controlled:

$$
e^{-S_{\mathrm{inst}}}\sim e^{-1/g^2}.
$$

That is nonperturbative because it is invisible to the power series in $g$, not because the coupling is large.

By contrast, a strongly coupled conformal field theory may have no small Lagrangian coupling at all. The term “nonperturbative” then means that the theory cannot be described by a weakly coupled expansion in the available variables. But the theory may still be exactly constrained by symmetry, duality, bootstrap, supersymmetric localization, or integrability.

There are therefore at least three different situations:

| Situation | Example | What “nonperturbative” means |
|---|---|---|
| Weak coupling with extra saddles | instantons in suitable regimes | Exponentially small terms not visible in loop expansion. |
| Strong coupling in chosen variables | infrared QCD | No small expansion in quarks and gluons at the scale of interest. |
| No known Lagrangian expansion | many CFTs and dual descriptions | The theory is defined or constrained by other data. |

Keeping these cases separate prevents a lot of fog.

## A toy model: why tunneling is invisible locally

Consider a symmetric double-well potential in quantum mechanics,

$$
V(q)=\frac{\lambda}{4}(q^2-v^2)^2.
$$

Near $q=+v$, write $q=v+\eta$. The Hamiltonian becomes a harmonic oscillator plus interactions in $\eta$. Perturbation theory gives energy levels localized near the right well. The same expansion near $q=-v$ gives localized levels near the left well.

But the exact eigenstates of the symmetric Hamiltonian are parity eigenstates. The two lowest states are approximately

$$
|+\rangle\sim \frac{1}{\sqrt2}(|L\rangle+|R\rangle),
\qquad
|-\rangle\sim \frac{1}{\sqrt2}(|L\rangle-|R\rangle),
$$

with an exponentially small energy splitting. Euclidean paths connecting the two minima—the instantons—supply the missing amplitude.

This example is humble but profound. It shows that perturbation theory can be perfectly correct about local oscillations and still wrong about the global spectrum.

In field theory, the same pattern reappears with more structure: degenerate vacua, domain walls, theta vacua, instantons, sphalerons, false-vacuum decay, and tunneling between sectors.

## A field-theory example: confinement is not a loop correction

Pure Yang–Mills theory at short distances is controlled by asymptotic freedom. At high momentum, perturbation theory around gluons is the correct language for many observables. The one-loop beta function already tells us that the coupling grows in the infrared.

But confinement is not the statement “the next loop is large.” It is a statement about the long-distance spectrum and extended operators. A standard diagnostic in pure gauge theory is the large-loop behavior

$$
\langle W(C)\rangle\sim e^{-\sigma\operatorname{Area}(C)}
$$

for suitable large loops. Equivalently, for a large rectangular loop,

$$
V(R)\sim \sigma R
$$

at large separation $R$, again in a regime where the diagnostic is appropriate.

No finite set of Feynman diagrams around $A_\mu=0$ proves this area law. The area law concerns coherent long-distance gauge-field configurations and the absence of isolated color charges. Lattice gauge theory, strong-coupling expansion, center symmetry, dual superconductor ideas, large-N reasoning, and generalized-symmetry language all give partial windows into this phenomenon.

The honest summary is: perturbation theory explains why short-distance QCD is weakly coupled; nonperturbative QFT is needed to explain why the long-distance spectrum is made of hadrons and glueballs rather than free quarks and gluons.

## Perturbative data can still know about nonperturbative physics

The phrase “beyond perturbation theory” can sound like perturbation theory should be discarded. That is not the modern view.

In many systems, the large-order growth of perturbative coefficients is controlled by nonperturbative saddles. Very schematically,

$$
a_n\sim \frac{n!}{A^n}
$$

may signal a singularity in the Borel plane associated with an action $A$. In favorable cases, perturbative series, instanton sectors, and other exponential sectors combine into a transseries,

$$
\mathcal O(g)\sim \sum_{k\geq0}\sigma^k e^{-kA/g^2}
\sum_{n\geq0}a_{k,n}g^n.
$$

This is the language of resurgence. The rough idea is that perturbation theory around one saddle can carry encoded information about other saddles, but extracting it requires more than ordinary finite-order perturbation theory.

This program is beautifully developed in quantum mechanics and many lower-dimensional or special QFT settings. In realistic four-dimensional gauge theories, the full story is more difficult. Renormalons, instantons, compactification, boundary conditions, complex saddles, and scheme dependence all enter. The safe lesson for now is not “perturbation theory secretly solves everything,” but rather “perturbative and nonperturbative sectors are often coupled more tightly than a first QFT course suggests.”

## How to recognize a nonperturbative question

A question is probably nonperturbative if it asks for any of the following:

| Question | Nonperturbative feature |
|---|---|
| Does the theory exist beyond formal perturbation theory? | Requires a definition, regulator, continuum limit, or axiomatic construction. |
| What is the exact vacuum? | May require minimizing the full quantum effective action or summing sectors. |
| Is there a mass gap? | Spectral and long-distance property. |
| Is the theory confining? | Extended operators and physical Hilbert space. |
| What are the phases? | Global long-distance behavior, not just local diagrams. |
| What is the tunneling rate? | Euclidean saddles and determinants. |
| How does theta dependence enter? | Sum over topological sectors. |
| Are there solitons or defects? | Boundary conditions and topology of configuration space. |
| What happens at finite density in real time? | Sign problem and non-equilibrium dynamics. |
| What is the exact answer at strong coupling? | May require duality, integrability, localization, bootstrap, or numerics. |

A question is probably perturbative if it asks for a coefficient in a controlled expansion around a known saddle, such as a one-loop anomalous dimension, a low-energy Wilson coefficient, a short-distance beta function, or a fixed-order scattering amplitude.

The word “probably” matters. The boundary is not moral; it is technical. Some quantities that look nonperturbative are protected by symmetry and can be computed exactly. Some quantities that look perturbative are contaminated by infrared effects and require nonperturbative input.

## How nonperturbative definitions enter

A formal expression such as

$$
\int\mathcal D\phi\,e^{-S_E[\phi]}
$$

is not automatically a definition. In perturbation theory, this may be enough because one only needs a rule for generating Gaussian integrals and counterterms. Nonperturbatively, one must ask harder questions:

- What is the regulator?
- What is the Hilbert space?
- Which fields or operators are genuine observables?
- Is the Euclidean measure positive?
- Does reflection positivity hold?
- How is the continuum limit taken?
- What boundary conditions and global sectors are summed over?
- Which symmetries are exact, anomalous, gauged, or explicitly broken?

Lattice field theory is the most concrete general answer for many Euclidean QFTs. It replaces continuum spacetime by a lattice, defines a finite-dimensional or well-regulated integral, and asks whether a continuum limit exists as the correlation length in lattice units diverges:

$$
\frac{\xi}{a}\to\infty.
$$

Constructive and algebraic approaches ask for mathematically sharper definitions. Hamiltonian truncation and tensor-network approaches define or approximate the Hilbert space more directly. The right definition depends on the theory and the question.

## Common pitfalls

### Thinking perturbation theory is “the theory”

Perturbation theory is a representation of some local information about a theory. It may be the only representation needed for a given observable at a given scale, but it is not automatically a complete definition.

### Thinking nonperturbative means “incalculable”

Many nonperturbative effects are calculable. The one-instanton contribution in a controlled semiclassical regime, the strong-coupling area law on a lattice, exact results in integrable models, supersymmetric localization formulas, and large-N saddle equations are all nonperturbative calculations.

### Confusing weak coupling with perturbative completeness

Weak coupling makes fluctuations small around a chosen saddle. It does not remove other saddles, topological sectors, tunneling paths, or exponentially small effects.

### Confusing strong coupling with deep physics

Strong coupling is not automatically profound. Sometimes it means the chosen variables are bad. A dual description may be weakly coupled, or a symmetry argument may bypass the coupling entirely.

### Treating the Lagrangian fields as physical particles

Fields in a Lagrangian are variables. Physical particles are states or excitations in the spectrum. In a confining theory, the elementary gauge-variant fields are not asymptotic particles.

### Ignoring the order of limits

Spontaneous symmetry breaking, confinement diagnostics, thermal limits, and infinite-volume limits can depend on order. A finite-volume answer may hide the phase structure that appears after the thermodynamic limit.

### Calling every hard problem nonperturbative

A difficult multiloop calculation is still perturbative if it asks for a coefficient in a loop expansion. Conversely, a conceptually simple tunneling splitting can be nonperturbative because every coefficient in the ordinary expansion misses it.

## Relations to other pages

- [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/) fixes the Euclidean, gauge, theta-angle, Wilson-loop, lattice, and large-N normalizations used here.
- The next conceptual page should be **Asymptotic Series and Missing Effects**, which explains asymptotic expansions, optimal truncation, Borel transforms, and exponentially small corrections more carefully.
- The later pages on nonperturbative observables, lattice regularization, instantons in quantum mechanics, Wilson-loop diagnostics, and what confinement means will turn the ideas on this page into concrete tests and calculations.

## Research status

- **Established:** Ordinary perturbation theory is an expansion around a chosen saddle or weakly coupled description. It often produces asymptotic series and misses effects such as tunneling amplitudes, instanton sectors, topological sectors, mass gaps, and confinement diagnostics.
- **Established:** Nonperturbative does not mean numerically large, and weakly coupled semiclassical effects can be nonperturbative in the expansion parameter.
- **Active:** The extent to which perturbative data determine nonperturbative sectors is an active research topic. Resurgence gives powerful answers in many quantum-mechanical, lower-dimensional, supersymmetric, compactified, or otherwise controlled settings, while realistic four-dimensional gauge theories remain subtler.
- **Active:** General-purpose nonperturbative real-time methods, finite-density methods, and controlled continuum Hamiltonian methods are major ongoing research directions.

## Exercises

### Exercise 1: A smooth function with zero Taylor series

Let

$$
f(g)=
\begin{cases}
 e^{-A/g^2}, & g>0,\\
 0, & g=0,
\end{cases}
\qquad A>0.
$$

Show that every derivative of $f$ at $g=0$ vanishes.

<details>
<summary><strong>Solution</strong></summary>

For $g>0$, every derivative has the form

$$
f^{(n)}(g)=P_n(1/g)e^{-A/g^2},
$$

where $P_n$ is a polynomial. This can be proved by induction: differentiating a polynomial in $1/g$ times $e^{-A/g^2}$ gives another polynomial in $1/g$ times $e^{-A/g^2}$.

For any integer $m\geq0$,

$$
\lim_{g\to0^+}g^{-m}e^{-A/g^2}=0,
$$

because the exponential decays faster than any power. Hence

$$
\lim_{g\to0^+}P_n(1/g)e^{-A/g^2}=0.
$$

Therefore $f^{(n)}(0)=0$ for every $n$. The Taylor series at zero is identically zero even though $f(g)>0$ for $g>0$.

</details>

### Exercise 2: One-loop dimensional transmutation

Assume

$$
\mu\frac{dg}{d\mu}=-b_0g^3,
\qquad b_0>0.
$$

Derive

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]
$$

as an RG-invariant scale at one loop.

<details>
<summary><strong>Solution</strong></summary>

Write the beta function as

$$
\frac{dg}{d\log\mu}=-b_0g^3.
$$

Then

$$
\frac{d}{d\log\mu}\left(\frac{1}{g^2}\right)
=-2g^{-3}\frac{dg}{d\log\mu}=2b_0.
$$

Integrating gives

$$
\frac{1}{g^2(\mu)}=2b_0\log\mu+\text{constant}.
$$

Choose the constant so that

$$
\frac{1}{g^2(\mu)}=2b_0\log\frac{\mu}{\Lambda}.
$$

Solving for $\Lambda$ gives

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

Differentiating this expression with respect to $\log\mu$ and using the beta function verifies that $\Lambda$ is invariant at this order.

</details>

### Exercise 3: Why a finite loop order cannot see an instanton

Suppose an observable has the schematic transseries

$$
\mathcal O(g)=\sum_{n=0}^{\infty}a_ng^{2n}+Ce^{-8\pi^2/g^2}\left(1+O(g^2)\right).
$$

Explain why no finite-order perturbative calculation in powers of $g^2$ can determine $C$.

<details>
<summary><strong>Solution</strong></summary>

A finite-order perturbative calculation determines only finitely many coefficients $a_0,\ldots,a_N$ in the power series. The function

$$
Ce^{-8\pi^2/g^2}\left(1+O(g^2)\right)
$$

has zero Taylor expansion at $g=0$. Adding it changes the exact function for every positive $g$, but it changes none of the coefficients $a_n$ in the ordinary Taylor expansion. Therefore finite-order perturbation theory cannot determine $C$.

In special problems, large-order perturbative behavior may encode information about such constants, but extracting that information is not the same as doing an ordinary finite-order loop calculation.

</details>

### Exercise 4: Local minima are not enough

Consider a quantum-mechanical double well with two degenerate minima. Explain in words why perturbation theory around one minimum gives two copies of the same local spectrum, while the exact spectrum has symmetric and antisymmetric combinations.

<details>
<summary><strong>Solution</strong></summary>

Perturbation theory around one minimum only uses the Taylor expansion of the potential near that minimum. It constructs wavefunctions localized in that well and computes oscillator-like corrections. The same construction around the other minimum gives an identical local spectrum.

The exact Hamiltonian knows about the whole potential, including the barrier and the other well. Since the potential is symmetric, exact eigenstates can be chosen with definite parity. The localized left and right states mix by tunneling through the barrier. The symmetric and antisymmetric combinations are split by an exponentially small amount controlled semiclassically by an instanton. That mixing is invisible in perturbation theory around either minimum alone.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially “Classical Lumps and Their Quantum Descendants,” “The Uses of Instantons,” and “1/N.”
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong-coupling expansion, instantons, confinement criteria, topology of gauge fields, loop dynamics, and large N.
- M. Mariño, *Instantons and Large N*, for instantons, large-order behavior, Borel summability, renormalons, Yang–Mills instantons, and large-N methods.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, 2nd ed., for phases of gauge theories, solitons, instantons, false-vacuum decay, anomalies, and confinement in lower-dimensional models.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., for field integrals, RG, critical phenomena, instantons, large-order behavior, and summation of perturbation theory.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” *Physics Reports* **12** (1974), for the Wilsonian viewpoint on critical phenomena and QFT.
- F. J. Dyson, “Divergence of Perturbation Theory in Quantum Electrodynamics,” *Physical Review* **85** (1952), for the classic instability argument about QED perturbation theory.
- G. ’t Hooft, “A Planar Diagram Theory for Strong Interactions,” *Nuclear Physics B* **72** (1974), for the large-N organization of gauge-theory perturbation theory.

## Version history

- **2026-06-25:** Initial polished draft. Added conceptual figure and exercises on zero Taylor series, dimensional transmutation, instanton invisibility, and tunneling in a double well.
