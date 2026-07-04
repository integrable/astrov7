---
title: "Euclidean Path Integral"
description: "Explains the Euclidean path integral as a nonperturbative definition candidate, including Schwinger functions, reflection positivity, spectra, and global definition data."
sidebar:
  label: "Euclidean Path Integral"
  order: 1
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader; Zinn-Justin; Srednicki; Schwartz; Wilson–Kogut; Glimm–Jaffe."
topics:
  - Euclidean path integral
  - Schwinger functions
  - reflection positivity
  - ground-state projection
  - spectral representation
  - nonperturbative definitions
canonicalTopics:
  - euclidean-qft
  - path-integral
  - reflection-positivity
  - nonperturbative-definition
  - spectral-representation
researchStatus:
  established:
    - "For many bosonic and gauge-invariant lattice systems with positive Euclidean weights, Euclidean correlation functions give a controlled nonperturbative route to spectra and static observables."
  active:
    - "Real-time observables, complex actions, finite density, chiral gauge theories, and continuum reconstruction outside controlled settings remain subtle and often require additional methods."
---

## Summary

The Euclidean path integral is the most common language for nonperturbative QFT. It replaces the oscillatory Lorentzian weight $e^{iS_M}$ by a Euclidean weight $e^{-S_E}$ and defines observables through Euclidean correlation functions,

$$
Z_E[J]
=\int_{\mathcal C}\mathcal D\Phi\,
\exp\left[-S_E[\Phi]+\int d^dx\,J(x)\mathcal O(x)\right],
$$

$$
\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle_E
=\frac{1}{Z_E[0]}
\int_{\mathcal C}\mathcal D\Phi\,
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)e^{-S_E[\Phi]}.
$$

The symbol $\mathcal C$ is not decorative. It includes the regulator, boundary conditions, field space, gauge quotient or gauge fixing, spin structure, topological-sector sum, and possible integration cycle. Nonperturbatively, these choices are part of the theory.

The Euclidean path integral matters because it can turn QFT into a statistical-mechanics-like problem. This is the basis of lattice field theory, finite-temperature QFT, instanton calculus, strong-coupling expansions, mass-gap diagnostics, and many constructive definitions. But the Euclidean integral is not automatically a Lorentzian QFT. To reconstruct a positive-norm Hilbert space, Euclidean correlators must obey conditions such as Euclidean invariance, locality, clustering, and especially reflection positivity.

:::note[Core distinction]
A formal continuum expression

$$
\int \mathcal D\Phi\,e^{-S_E[\Phi]}
$$

is not yet a nonperturbative definition. A definition is a regulated family of such objects, together with observables and a limit in which physical quantities are held fixed.
:::

## Prerequisites

You should know Gaussian path integrals, time-ordered correlation functions, Wick rotation in elementary examples, and the meaning of a Hamiltonian spectrum. You should also be comfortable with the volume conventions fixed in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

Useful conceptual preparation comes from [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/) and [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/). This page supplies the definition-level language used later for lattice regularization, continuum limits, instantons, Wilson loops, finite-temperature QFT, and mass gaps.

## Core idea

The Euclidean path integral is useful because Euclidean time evolution is damping rather than oscillatory. In quantum mechanics,

$$
K_E(q_f,\tau_f;q_i,\tau_i)
=\langle q_f|e^{-(\tau_f-\tau_i)H}|q_i\rangle,
\qquad \tau_f>\tau_i.
$$

Inserting energy eigenstates gives

$$
K_E(q_f,T;q_i,0)
=\sum_n \psi_n(q_f)\psi_n^*(q_i)e^{-T E_n}.
$$

As $T\to\infty$, the lowest energy state dominates. This is the whole secret behind many Euclidean methods: Euclidean time projects onto low-energy physics.

The same idea holds in QFT. A Euclidean two-point function of an operator $\mathcal O$ often has the spectral form

$$
C(\tau)
=\int d^D\mathbf x\,\langle\mathcal O(\tau,\mathbf x)\mathcal O(0,\mathbf 0)\rangle_{E,c}
=\sum_{n\neq0}|\langle0|\mathcal O|n\rangle|^2e^{-\tau(E_n-E_0)},
$$

for $\tau>0$, in a finite spatial volume or in a setting where the spectral decomposition is well-defined. At large $\tau$, the leading exponential gives the lightest state coupled to $\mathcal O$. This is why Euclidean correlators are not merely formal Green functions: they are a direct route to masses, gaps, string tensions, susceptibilities, and matrix elements.

A useful slogan is

$$
\text{Euclidean path integral} = \text{statistical mechanics of fields} + \text{Hilbert-space reconstruction data}.
$$

The first half makes computations possible. The second half prevents the computation from drifting away from quantum theory.

## Setup and conventions

This page uses the Euclidean conventions from [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). Lorentzian time is continued as

$$
t=-i\tau,
$$

and the Euclidean weight is $e^{-S_E}$. In Euclidean signature, contractions use $\delta_{\mu\nu}$, and the momentum-space scalar propagator for a free massive field is

$$
G_E(p)=\frac{1}{p_E^2+m^2}.
$$

For a real scalar field,

$$
S_E[\phi]
=\int d^dx\left[\frac12(\partial_\mu\phi)^2+V(\phi)\right].
$$

For example, with

$$
V(\phi)=\frac12m_0^2\phi^2+\frac{\lambda_0}{4!}\phi^4,
$$

a finite-cutoff version of the scalar Euclidean path integral can be made into an ordinary finite-dimensional integral, for example by putting the theory on a finite lattice. The continuum expression is shorthand for such a limiting construction.

For Yang–Mills theory in the geometric normalization used in this volume,

$$
S_{E,\mathrm{YM}}
=\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}-i\theta Q,
$$

where

$$
Q=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

The positive Yang–Mills term is suitable for Euclidean damping. The theta term is imaginary in Euclidean signature, so $\theta\neq0$ generally produces a complex weight. This is one of the first places where the phrase “Euclidean path integral” stops meaning “ordinary probability distribution.”

The Euclidean source convention is

$$
Z_E[J]
=\int_{\mathcal C}\mathcal D\Phi\,e^{-S_E[\Phi]+\int J\mathcal O},
\qquad
W_E[J]=\log Z_E[J].
$$

Connected Euclidean correlators are obtained from $W_E[J]$ by functional differentiation. The exact quantum effective action is the Legendre transform when the necessary convexity and source assumptions hold; a loop-expanded effective action around one saddle is a different, local object.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A map from regulated Euclidean path integrals to Schwinger functions, positivity, Hilbert-space reconstruction, and Lorentzian observables.](/figures/nonperturbative-qft/euclidean-reconstruction-map.svg)

<figcaption>

The Euclidean route to QFT data. A regulated Euclidean integral defines Schwinger functions. With reflection positivity and the remaining reconstruction conditions, these data determine a Hilbert space, Hamiltonian, and Lorentzian Wightman theory. Without positivity, the Euclidean integral may still be useful, but it is not automatically a standard quantum theory.

</figcaption>
</figure>

## From Lorentzian amplitudes to Euclidean kernels

The safest way to understand Wick rotation is to begin with ordinary quantum mechanics. The Lorentzian transition amplitude is

$$
K_M(q_f,t_f;q_i,t_i)
=\langle q_f|e^{-i(t_f-t_i)H}|q_i\rangle.
$$

For $t_f-t_i=-iT$ with $T>0$, this becomes

$$
K_E(q_f,T;q_i,0)
=\langle q_f|e^{-T H}|q_i\rangle.
$$

If the Hamiltonian is

$$
H=\frac{p^2}{2m}+V(q),
$$

then the Euclidean action is

$$
S_E[q]
=\int_0^T d\tau\left[\frac{m}{2}\left(\frac{dq}{d\tau}\right)^2+V(q)\right],
$$

and the kernel is represented formally by

$$
K_E(q_f,T;q_i,0)
=\int_{q(0)=q_i}^{q(T)=q_f}\mathcal Dq\,e^{-S_E[q]}.
$$

This formula can be derived by time slicing. Divide $T$ into $N$ intervals of size $\epsilon=T/N$ and insert $N-1$ resolutions of the identity in the position basis. One obtains an ordinary multiple integral,

$$
K_E(q_f,T;q_i,0)
=\lim_{N\to\infty}\left(\frac{m}{2\pi\epsilon}\right)^{N/2}
\int\prod_{k=1}^{N-1}dq_k\,
\exp\left[-\sum_{k=0}^{N-1}\epsilon\left(\frac{m}{2}\left(\frac{q_{k+1}-q_k}{\epsilon}\right)^2+V(q_k)\right)\right],
$$

up to harmless choices in the discretization of $V$. This time-sliced formula shows what the functional integral really means in this simple case: a limit of finite-dimensional integrals.

The same lesson carries to QFT. A continuum Euclidean functional integral should be understood through a regulator: a spatial lattice, spacetime lattice, momentum cutoff, finite-mode truncation, heat-kernel regulator, or some other construction. Different regulators may define the same continuum theory, but that is a theorem or physical universality statement, not something built into the symbol $\mathcal D\Phi$.

## Schwinger functions

Euclidean correlation functions are often called Schwinger functions. For scalar fields,

$$
S_n(x_1,\ldots,x_n)
=\langle\phi(x_1)\cdots\phi(x_n)\rangle_E.
$$

For composite or gauge-invariant operators,

$$
S_{\mathcal O_1\cdots\mathcal O_n}(x_1,\ldots,x_n)
=\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle_E.
$$

In a nonperturbative setting, Schwinger functions are often more fundamental than fields in a Lagrangian. They are the quantities one estimates on the lattice, constrains by symmetry, reconstructs into spectral data, and compares across regulators.

For a free scalar field,

$$
S_2(x)
=\int\frac{d^dp}{(2\pi)^d}\,\frac{e^{ip\cdot x}}{p^2+m^2}.
$$

At large Euclidean separation, this decays exponentially for $m>0$:

$$
S_2(x)\sim \frac{e^{-m|x|}}{|x|^{(d-1)/2}}
$$

up to a dimension-dependent constant. The exponential decay encodes the mass gap in the one-particle channel. In an interacting theory, the large-distance decay of suitable connected correlators similarly diagnoses the lowest excitation coupled to the chosen operator.

Schwinger functions also encode symmetry. If the Euclidean theory is invariant under translations and rotations, then

$$
S_n(x_1+a,\ldots,x_n+a)=S_n(x_1,\ldots,x_n)
$$

and scalar two-point functions depend only on $|x_1-x_2|$. Gauge theories require gauge-invariant operators or a gauge-fixed treatment with BRST care; the nonperturbative observables are usually Wilson loops, Polyakov loops, local gauge-invariant composites, and correlators of such objects.

## The finite-volume trace picture

For many purposes, the cleanest definition is not an infinite-volume vacuum integral but a finite-volume trace. Put the theory in a spatial box of volume $L^D$ with chosen boundary conditions. Then the zero-temperature Euclidean expectation value is obtained from

$$
Z_L(T)=\operatorname{Tr}_{\mathcal H_L}e^{-T H_L}.
$$

For an operator inserted at Euclidean time $\tau$,

$$
\langle\mathcal O(\tau)\mathcal O(0)\rangle_{L,T}
=\frac{1}{Z_L(T)}\operatorname{Tr}\left(e^{-(T-\tau)H_L}\mathcal O e^{-\tau H_L}\mathcal O\right).
$$

Taking $T\to\infty$ projects onto the finite-volume ground state:

$$
\lim_{T\to\infty}\langle\mathcal O(\tau)\mathcal O(0)\rangle_{L,T}
=\sum_n |\langle 0,L|\mathcal O|n,L\rangle|^2e^{-\tau(E_n(L)-E_0(L))}.
$$

Only after this finite-volume object is understood should one ask for $L\to\infty$. This order matters. Spontaneous symmetry breaking, degenerate vacua, tunneling splittings, topological sectors, and massless modes can behave differently depending on whether one takes infinite time, infinite volume, and zero source in the right order.

At finite temperature,

$$
Z_L(\beta)=\operatorname{Tr}_{\mathcal H_L}e^{-\beta H_L},
$$

and Euclidean time is a circle of circumference $\beta$. Bosonic fields are periodic around the thermal circle, while fermionic fields are antiperiodic for the ordinary thermal partition function:

$$
\phi(\tau+\beta,\mathbf x)=\phi(\tau,\mathbf x),
\qquad
\psi(\tau+\beta,\mathbf x)=-\psi(\tau,\mathbf x).
$$

Different spin structures or twisted boundary conditions define different traces, such as supersymmetric indices or partition functions with symmetry insertions.

## Reflection positivity

Euclidean invariance alone is not enough to guarantee a Lorentzian quantum theory. The missing ingredient is positivity of the Hilbert-space norm. In Euclidean language, this appears as reflection positivity.

Let $\Theta$ reflect Euclidean time,

$$
\Theta:(\tau,\mathbf x)\mapsto(-\tau,\mathbf x),
$$

and complex conjugate coefficients in correlation functions. Let $F_i$ be functionals of fields supported at positive Euclidean time $\tau>0$. Reflection positivity says

$$
\sum_{i,j}\overline{c_i}c_j\,\langle(\Theta F_i)F_j\rangle_E\geq0
$$

for all complex coefficients $c_i$.

This condition is easy to motivate from the operator trace. If $F$ is built from operators at positive Euclidean times, then in a Hamiltonian theory the reflected insertion $\Theta F$ acts like the adjoint of $F$. The expectation value

$$
\langle(\Theta F)F\rangle_E
$$

is therefore the Euclidean version of a norm squared. The abstract reconstruction theorem reverses this logic: if Euclidean correlators obey suitable axioms including reflection positivity, one can reconstruct a Hilbert space, a vacuum, a positive Hamiltonian, and Lorentzian Wightman functions.

This is why reflection positivity is not a technical footnote. It is the condition that stops an arbitrary Euclidean statistical model from masquerading as a unitary Lorentzian QFT.

:::caution[Positive Euclidean weight is not the same as reflection positivity]
A real positive Boltzmann weight is helpful, especially for Monte Carlo methods, but reflection positivity is a more structured statement involving time reflection and operator support. Conversely, gauge fixing, fermions, and auxiliary fields can obscure positivity even when the physical gauge-invariant sector is expected to be unitary.
:::

## Reconstruction in words

The Osterwalder–Schrader reconstruction idea can be summarized as follows.

First, start with Euclidean correlation functions $S_n$ satisfying the Euclidean axioms: symmetry under permutations of bosonic insertions, Euclidean invariance, regularity, clustering, and reflection positivity.

Second, build a vector space from functionals $F$ supported at positive Euclidean time. Define an inner product by

$$
(F,G)=\langle(\Theta F)G\rangle_E.
$$

Reflection positivity says this inner product is positive semidefinite. Null vectors are quotiented out, and the completion gives the Hilbert space.

Third, positive Euclidean time translations act as contraction operators. Their generator is identified with the Hamiltonian $H$, with

$$
T(a)=e^{-aH},\qquad a>0.
$$

Fourth, under suitable analytic continuation, Euclidean Schwinger functions give Lorentzian Wightman functions. These Wightman functions obey locality, spectral positivity, and the usual Hilbert-space interpretation.

For this page, the point is not to prove the theorem. The point is to know what must be true for the Euclidean path integral to define a quantum field theory rather than merely a Euclidean statistical model.

## Gauge theories and quotienting

Gauge fields add a subtlety: the path integral should not integrate over physically equivalent configurations as if they were distinct. Formally, one writes

$$
Z_E=\frac{1}{\operatorname{Vol}\mathcal G}\int\mathcal DA\,e^{-S_E[A]},
$$

where $\mathcal G$ is the gauge group. This expression is symbolic; the volume of the gauge group is infinite, and the quotient can have global complications.

There are three common physics routes.

First, one may gauge-fix and include Faddeev–Popov ghosts, BRST symmetry, and gauge-fixed propagators. This is convenient for perturbation theory and continuum formal work.

Second, one may use a lattice gauge theory with compact link variables. The gauge-invariant measure is then an ordinary product of Haar measures over links before the continuum limit is taken. Gauge-invariant observables such as Wilson loops can be defined without gauge fixing.

Third, one may focus directly on gauge-invariant operator algebras, line operators, sectors, and boundary conditions. This route becomes essential when the global form of the gauge group or the spectrum of allowed line operators matters.

The Euclidean path integral must also specify topological sectors. In four-dimensional Yang–Mills theory, for example,

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q,
\qquad
Z_Q=\int_{\mathcal C_Q}\mathcal DA\,e^{-S_{E,0}[A]}.
$$

The sector sum is not visible in ordinary perturbation theory around $A=0$, but it changes physical observables such as theta dependence and topological susceptibility.

## Euclidean observables

The Euclidean path integral naturally computes observables that are invariantly defined in Euclidean signature. The most common examples are:

| Observable | Euclidean expression | What it diagnoses |
|---|---|---|
| Mass or gap | Exponential decay of connected two-point functions | Spectrum and correlation length |
| Static potential | Large rectangular Wilson loops | Confinement, screening, string tension |
| Thermal free energy | $F=-(1/\beta)\log Z(\beta)$ | Phases and thermodynamics |
| Susceptibility | Integrated connected correlator | Response to sources and order-parameter fluctuations |
| Topological susceptibility | $\chi_t=\langle Q^2\rangle/V$ at $\theta=0$ | Theta dependence and topology |
| Condensate | Source derivative of $\log Z$ | Symmetry realization and vacuum structure |
| Matrix element | Large-time ratios of correlators | Hadronic and finite-volume observables |

The mass-gap example is worth isolating. If

$$
C(\tau)\sim A e^{-\Delta\tau}
$$

at large $\tau$, then $\Delta$ is the lowest excitation energy in the channel created by $\mathcal O$. A poor choice of $\mathcal O$ may have small or zero overlap with the lightest state, so operator choice is part of the practical nonperturbative problem.

Wilson loops provide a second canonical example. For a rectangular loop of spatial size $R$ and Euclidean time length $T$,

$$
\langle W(R,T)\rangle\sim e^{-T V(R)}
$$

as $T\to\infty$. If

$$
V(R)\sim \sigma R
$$

at large $R$, then the loop exhibits an area law,

$$
\langle W(R,T)\rangle\sim e^{-\sigma RT},
$$

with string tension $\sigma$. This is a Euclidean diagnostic of confinement for external probe charges, subject to the usual caveats about matter content, representation, screening, and center symmetry.

## What Euclidean methods do not automatically give

Euclidean correlators are powerful, but they do not make every nonperturbative problem easy.

First, real-time dynamics requires analytic continuation. A Euclidean two-point function at discrete imaginary times may determine a spectral density in principle, but extracting that density from noisy or incomplete data is an ill-posed inverse problem. This is why transport coefficients, scattering, and time-dependent response are much harder than static masses.

Second, complex weights obstruct probability sampling. A theta term, chemical potential, real-time contour, or chiral determinant can make the weight nonpositive or complex. Then importance sampling based on $e^{-S_E}$ as a probability measure fails or becomes exponentially hard.

Third, Euclidean methods can hide sign and positivity issues. A formal manipulation may produce reasonable-looking Euclidean correlators that do not satisfy reflection positivity. Such correlators cannot reconstruct a standard unitary Lorentzian QFT without further work.

Fourth, gauge-variant Euclidean quantities are not automatically physical. A gauge-fixed gluon propagator can be useful, but confinement and the physical spectrum are statements about gauge-invariant observables and the physical Hilbert space.

Fifth, continuum extrapolation is a separate problem. A finite lattice computation gives a regulated answer. To claim a continuum QFT, one must show scaling toward a continuum limit and control dependence on lattice spacing, volume, boundary conditions, and operator renormalization.

## Common pitfalls

**Pitfall 1: treating $\mathcal D\Phi$ as a measure without a regulator.** In most interacting continuum QFTs, the formal functional measure is not defined by the notation alone. Start from a finite-dimensional or otherwise regulated object.

**Pitfall 2: confusing Euclidean time ordering with Lorentzian time ordering.** Euclidean correlators are ordered by imaginary time. Their analytic continuation can produce Lorentzian Wightman, time-ordered, retarded, or advanced functions only after specifying domains, $i\epsilon$ prescriptions, and spectral information.

**Pitfall 3: assuming a positive-looking Euclidean action guarantees unitarity.** Reflection positivity is the relevant Hilbert-space condition. Some discretizations or higher-derivative regulators improve ultraviolet behavior but violate reflection positivity.

**Pitfall 4: forgetting global sectors.** Instantons, theta vacua, winding sectors, spin structures, line operators, and boundary conditions can be invisible in perturbation theory but essential nonperturbatively.

**Pitfall 5: extracting a mass from too-short Euclidean times.** The correlator

$$
C(\tau)=\sum_n A_n e^{-E_n\tau}
$$

contains excited states at finite $\tau$. A convincing mass extraction must control excited-state contamination, finite-volume effects, and operator overlap.

**Pitfall 6: calling every Euclidean statistical system a QFT.** A Euclidean lattice model can define a statistical system. It defines a Lorentzian QFT only when the continuum limit and reconstruction conditions support that interpretation.

## Relations to other pages

This page is the definition-level bridge between the conceptual chapter and later physics chapters.

- [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/) fixes the Euclidean sign choices, gauge-field normalization, theta-sector notation, and finite-temperature conventions used here.
- [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) explains why the observables computed by Euclidean methods are often spectra, Wilson loops, gaps, and response functions rather than elementary field amplitudes.
- Lattice Regularization makes the formal Euclidean integral finite by replacing fields with a finite set of variables.
- Continuum Limit explains how a regulated Euclidean system becomes a continuum QFT through scaling and renormalization.
- Reflection Positivity develops the Hilbert-space reconstruction condition in more detail.
- Instantons in Field Theory, Theta Vacua, and Topological Susceptibility use Euclidean sector sums and saddle points.
- Wilson Loop Diagnostics and Wilson Loop Area Law use Euclidean rectangular loops to diagnose static potentials and confinement.

## Research status

**Established.** Euclidean path integrals, Schwinger functions, transfer matrices, and reflection positivity provide a standard nonperturbative framework for many QFTs and statistical field theories. Lattice regularization makes this framework concrete for scalar theories, vectorlike gauge theories, many spin systems, and a large class of Euclidean statistical models.

**Established with caveats.** Perturbative Wick rotation is highly successful in ordinary local QFT under the usual spectral and analyticity assumptions. Nonperturbatively, one must check the Euclidean definition, positivity, regulator, and continuum limit.

**Active.** Real-time reconstruction from Euclidean data, finite-density systems with sign problems, chiral gauge theories on the lattice, nonperturbative definitions of some continuum gauge theories, and complex saddle decompositions are active areas. They are not failures of the Euclidean method; they are places where the simple $e^{-S_E}$ picture is not the whole story.

## Exercises

### Exercise 1: Ground-state projection

Let $H|n\rangle=E_n|n\rangle$ with $E_0<E_1\leq E_2\leq\cdots$. Let $|\Psi\rangle$ be a state with $\langle0|\Psi\rangle\neq0$. Show that

$$
\frac{e^{-T H}|\Psi\rangle}{\|e^{-T H}|\Psi\rangle\|}
$$

approaches the ground state as $T\to\infty$, up to a phase, and estimate the leading correction.

<details><summary><strong>Solution</strong></summary>

Expand

$$
|\Psi\rangle=\sum_n c_n|n\rangle,
\qquad c_0\neq0.
$$

Then

$$
e^{-T H}|\Psi\rangle
=e^{-T E_0}\left(c_0|0\rangle+\sum_{n>0}c_ne^{-T(E_n-E_0)}|n\rangle\right).
$$

The common factor $e^{-T E_0}$ is removed by normalization. The leading correction is controlled by the smallest gap $E_1-E_0$ for which $c_1\neq0$:

$$
\text{correction}=O(e^{-T(E_1-E_0)}).
$$

If the initial state has zero overlap with the first excited states in some symmetry sector, the leading correction comes from the lightest state with nonzero overlap.

</details>

### Exercise 2: Free Euclidean propagator

For the free scalar Euclidean action

$$
S_E[\phi]=\frac12\int d^dx\,\phi(-\partial^2+m^2)\phi,
$$

show that

$$
\langle\phi(x)\phi(0)\rangle_E
=\int\frac{d^dp}{(2\pi)^d}\frac{e^{ip\cdot x}}{p^2+m^2}.
$$

<details><summary><strong>Solution</strong></summary>

The generating functional is Gaussian:

$$
Z[J]\propto
\exp\left[\frac12\int d^dx\,d^dy\,J(x)K^{-1}(x,y)J(y)\right],
$$

where

$$
K=-\partial^2+m^2.
$$

Therefore

$$
\langle\phi(x)\phi(y)\rangle_E=K^{-1}(x,y).
$$

In momentum space, $K$ multiplies by $p^2+m^2$, so

$$
K^{-1}(x,y)=\int\frac{d^dp}{(2\pi)^d}\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

Setting $y=0$ gives the result.

</details>

### Exercise 3: Spectral decay of a two-point function

Assume a finite-volume Hamiltonian with eigenstates $|n\rangle$. Let $\mathcal O$ be an operator with $\langle0|\mathcal O|0\rangle=0$. Show that

$$
C(\tau)=\langle0|\mathcal O(\tau)\mathcal O(0)|0\rangle_E
$$

has the form

$$
C(\tau)=\sum_{n>0}|\langle0|\mathcal O|n\rangle|^2e^{-\tau(E_n-E_0)}.
$$

<details><summary><strong>Solution</strong></summary>

In Euclidean time,

$$
\mathcal O(\tau)=e^{\tau H}\mathcal O e^{-\tau H}.
$$

Insert a complete set of energy eigenstates between the two operators:

$$
C(\tau)
=\sum_n\langle0|e^{\tau H}\mathcal Oe^{-\tau H}|n\rangle\langle n|\mathcal O|0\rangle.
$$

Using $H|n\rangle=E_n|n\rangle$ and $\langle0|H=E_0\langle0|$ gives

$$
C(\tau)=\sum_n e^{-\tau(E_n-E_0)}\langle0|\mathcal O|n\rangle\langle n|\mathcal O|0\rangle.
$$

If $\mathcal O$ is Hermitian, the matrix-element product is $|\langle0|\mathcal O|n\rangle|^2$. The $n=0$ term vanishes because $\langle0|\mathcal O|0\rangle=0$.

</details>

### Exercise 4: Reflection positivity in one line

Let $F=\sum_i c_i F_i$ be a linear combination of functionals supported at positive Euclidean time. Show that the matrix

$$
M_{ij}=\langle(\Theta F_i)F_j\rangle_E
$$

must be positive semidefinite if reflection positivity holds.

<details><summary><strong>Solution</strong></summary>

Reflection positivity states that

$$
\langle(\Theta F)F\rangle_E\geq0
$$

for every such $F$. Substituting $F=\sum_i c_iF_i$ gives

$$
\langle(\Theta F)F\rangle_E
=\sum_{i,j}\overline{c_i}c_j\langle(\Theta F_i)F_j\rangle_E
=\sum_{i,j}\overline{c_i}M_{ij}c_j\geq0.
$$

This is precisely the definition that $M$ is positive semidefinite.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, chapters on path integrals in quantum mechanics and QFT, fermionic path integrals, nonabelian gauge-theory path integrals, and Wilson loops/lattice theory/confinement.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on path integrals, Schwinger–Dyson equations, Yang–Mills theory, and lattice gauge theories.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the Euclidean field-integral formulation and its connection to statistical mechanics and critical phenomena.

### Deeper references

- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green’s Functions,” for reflection positivity and Euclidean reconstruction.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for a constructive treatment of Euclidean functional integrals.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the Wilsonian/statistical-mechanics viewpoint and exact RG ideas.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling expansions, gauge-field topology, loop variables, and Euclidean nonperturbative methods.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, and A. Altland and B. Simons, *Condensed Matter Field Theory*, for Euclidean path integrals in statistical and condensed-matter settings.

## Version history

- **2026-06-25:** Initial polished page.
