---
title: "Nonperturbative Observables"
description: "A guide to the observables that diagnose nonperturbative QFT: spectra, correlators, Wilson loops, disorder operators, background-field partition functions, and phase diagnostics."
sidebar:
  label: "Nonperturbative Observables"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki; Polyakov; Shifman; Gaiotto–Kapustin–Seiberg–Willett; Zinn-Justin; Casini–Huerta."
topics:
  - observables
  - Wilson loops
  - mass gap
  - disorder operators
  - topological sectors
  - generalized global symmetries
canonicalTopics:
  - nonperturbative-observables
  - wilson-loops
  - mass-gap
  - line-operators
  - order-parameters
  - generalized-global-symmetries
researchStatus:
  established:
    - "Nonperturbative phenomena are often diagnosed by gauge-invariant local correlators, spectra, extended operators, defect insertions, and partition functions with specified global data."
  active:
    - "Modern work continues to refine the correct global and categorical language for line operators, defects, generalized symmetries, and phase diagnostics beyond ordinary local order parameters."
---

## Summary

Nonperturbative QFT is, to a large extent, the art of asking questions in the right observables. The elementary fields in a Lagrangian are often not the physical particles, not gauge-invariant, and not the best diagnostics of a phase. The correct observable might be a large Wilson loop, a finite-volume energy level, a defect operator, a theta-dependent partition function, a topological susceptibility, an entanglement quantity, or the long-distance decay of a gauge-invariant correlator.

The guiding rule is:

$$
\text{choose an observable whose support and symmetry charge match the phenomenon.}
$$

For example, a mass gap is visible in the exponential decay of correlators or in the finite-volume spectrum. Confinement in pure gauge theory is diagnosed by large Wilson loops and center symmetry, not by the gluon propagator alone. Theta dependence is encoded in sums over topological sectors. A higher-form symmetry is detected by extended operators, not by local charged fields. A topological phase may require ground-state degeneracy, line operators, or partition functions on nontrivial manifolds.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Map of nonperturbative observables](/figures/nonperturbative-qft/nonperturbative-observables-map.svg)

<figcaption>

Nonperturbative observables are not all local. Local correlators, spectra, line operators, disorder defects, thermal loops, and background-field partition functions diagnose different pieces of the same QFT.

</figcaption>
</figure>

The main danger is trying to diagnose every phase by a vacuum expectation value of an elementary field. That works beautifully for some symmetry-breaking problems and fails spectacularly for confinement, topological order, generalized symmetries, and gauge theories with screening.

## Prerequisites

You should have read [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/) and [Semiclassical versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/). The notation for Euclidean expectation values, Wilson loops, Polyakov loops, theta sums, and genuine line operators follows [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

This page assumes basic familiarity with correlation functions and gauge invariance. It does not assume prior knowledge of lattice gauge theory or generalized global symmetries.

## Core idea

An observable is not merely something one can write in terms of fields. It must be well-defined in the theory. In a nonperturbative setting this usually means specifying:

| Data | Why it matters |
|---|---|
| Support | Is the observable local, a line, a surface, a defect, a boundary condition, or a whole-spacetime quantity? |
| Gauge invariance | Gauge-variant fields may be useful variables, but they are not physical observables by themselves. |
| Symmetry charge | The observable may be charged under ordinary or higher-form global symmetries. |
| Regulator definition | The observable must make sense before taking the continuum limit. |
| Limit order | Infinite volume, zero source, continuum limit, large loop, and large time limits may not commute. |
| Global data | Gauge-group global form, allowed line operators, spin structure, theta angle, and background fields can change the answer. |

Perturbative QFT often trains us to calculate Green functions of elementary fields. Nonperturbative QFT asks a sharper question: which gauge-invariant, regulator-defined, symmetry-aware quantity sees the phenomenon?

This is why observables appear so early in this volume. A bad observable can make a simple phase look mysterious. A good observable can make a hard phenomenon sharply diagnosable even before it is fully solved.

## Setup and conventions

A Euclidean expectation value is written

$$
\langle\mathcal O\rangle
=\frac{1}{Z}\int_{\mathcal C}\mathcal D\Phi\,\mathcal O[\Phi]e^{-S_E[\Phi]},
\qquad
Z=\int_{\mathcal C}\mathcal D\Phi\,e^{-S_E[\Phi]}.
$$

The symbol $\mathcal C$ is part of the definition. It may include boundary conditions, a regulator, a sum over topological sectors, a choice of spin structure, a gauge bundle, or an integration cycle. This is not decorative notation. Nonperturbative observables often depend on exactly these data.

Connected correlators are generated by

$$
W[J]=\log Z[J],
$$

where

$$
Z[J]=\int\mathcal D\Phi\,\exp\left[-S_E[\Phi]+\int d^dx\,J(x)\mathcal O(x)\right].
$$

A vacuum expectation value, condensate, or order parameter is often defined by differentiating the free-energy density with respect to a source. If $V$ is the Euclidean spacetime volume,

$$
w[J]=\frac{1}{V}\log Z[J],
\qquad
\langle\mathcal O\rangle_J=\frac{\delta w[J]}{\delta J}.
$$

For spontaneous symmetry breaking, the order of limits is essential:

$$
\langle\mathcal O\rangle_{\mathrm{SSB}}
=\lim_{J\to0}\lim_{V\to\infty}\langle\mathcal O\rangle_J.
$$

At finite volume and zero source, an exact symmetry usually forces the expectation value of a charged order parameter to vanish.

## Local correlators and the mass gap

Local gauge-invariant operators are still one of the main windows into nonperturbative QFT. Let $\mathcal O(x)$ be a local operator with the quantum numbers of interest. In a Euclidean theory with a mass gap, the connected two-point function often decays as

$$
\langle\mathcal O(x)\mathcal O(0)\rangle_c
\sim
\frac{e^{-m_{\mathcal O}|x|}}{|x|^{\alpha}}
\qquad |x|\to\infty,
$$

where $m_{\mathcal O}$ is the mass of the lightest state that couples to $\mathcal O$, and the power $\alpha$ depends on dimension and spin. More invariantly, with Euclidean time separation $\tau$,

$$
C_{\mathcal O}(\tau)
=\langle \mathcal O(\tau)\mathcal O(0)\rangle_c
=\sum_{n\neq0}|\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)\tau}.
$$

At large $\tau$, the smallest energy difference with nonzero matrix element dominates. This is the basic reason lattice calculations extract masses from exponential falloff.

A theory has a mass gap if there is a positive lower bound

$$
\Delta=\inf_{n\neq0}(E_n-E_0)>0
$$

above the vacuum in infinite volume, after accounting for superselection sectors and possible degeneracies. In practice, one diagnoses the gap through spectra, exponential clustering, transfer-matrix eigenvalues, or spectral densities.

:::note[The operator matters]
A correlator sees only states with the same quantum numbers as the operator. If $\mathcal O$ has zero overlap with the lightest particle, its long-distance decay measures a different mass. This is a feature, not a bug: operators select channels.
:::

## Spectral observables

Sometimes the cleanest observable is the spectrum itself. In finite spatial volume $L$, one can study energy levels

$$
E_0(L),E_1(L),E_2(L),\ldots.
$$

The infinite-volume physics is encoded in how these levels scale with $L$. A massive isolated particle gives levels approaching a mass shell. A conformal field theory has finite-volume energies related to scaling dimensions in special geometries. A confining gauge theory has glueball and flux-tube spectra. A theory with spontaneous symmetry breaking may have nearly degenerate vacua with splittings that vanish exponentially with volume.

Spectral observables are especially useful because they do not require identifying elementary particles in the Lagrangian. They ask directly: what states exist in the Hilbert space?

In a Lorentz-invariant theory, spectral densities also give nonperturbative information. The Källén–Lehmann representation for a scalar operator has the schematic form

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
=\int_0^\infty d\mu^2\,\rho_{\mathcal O}(\mu^2)\Delta_E(x;\mu^2),
$$

where $\rho_{\mathcal O}$ is positive in a unitary theory for suitable Hermitian $\mathcal O$. Poles, thresholds, and continuum support encode stable particles, multi-particle states, and bound states.

## Condensates and local order parameters

A local order parameter is an operator whose expectation value distinguishes phases, often by transforming nontrivially under a symmetry. In a ferromagnet, magnetization is the prototype. In a relativistic scalar theory with a broken $\mathbb Z_2$ symmetry, one may use

$$
\langle\phi\rangle\neq0
$$

after taking the infinite-volume and zero-source limits in the correct order.

In QFT, local order parameters require care for three reasons.

First, the operator may need renormalization. A composite operator such as $\phi^2$ or $\bar\psi\psi$ can mix with other operators and may depend on scheme and scale. A condensate can be meaningful, but its normalization is not automatically universal.

Second, a gauge-variant field expectation value is not a gauge-invariant observable. In a gauge theory, statements like $\langle\phi\rangle\neq0$ can be gauge-dependent unless phrased through gauge-invariant operators, gauge-fixed diagnostics with care, or the pattern of global symmetries and spectra.

Third, not all phases are distinguished by local order parameters. Topological phases, confinement with screening, and phases distinguished by higher-form symmetries may require extended operators or global observables.

A safe definition of a local order parameter uses a source:

$$
Z[J]=\int\mathcal D\Phi\,e^{-S_E+J\int d^dx\,\mathcal O(x)},
$$

then takes

$$
\langle\mathcal O\rangle=\lim_{J\to0}\lim_{V\to\infty}\frac{1}{V}\frac{\partial\log Z[J]}{\partial J}.
$$

The source selects a vacuum before the thermodynamic limit removes tunneling between degenerate vacua.

## Wilson loops

For a closed curve $C$ and representation $R$, the Wilson loop is

$$
W_R(C)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P\exp\left(-i\oint_C A\right).
$$

Wilson loops are among the most important nonperturbative observables in gauge theory. They are gauge-invariant extended operators and can diagnose confinement, screening, center symmetry realization, and the behavior of static external charges.

For a large rectangular loop of spatial size $R$ and Euclidean time size $T$,

$$
\langle W(R,T)\rangle\sim e^{-T V(R)}
\qquad T\to\infty,
$$

where $V(R)$ is the static potential between external test charges in representation $R$, when that interpretation is available. An area law

$$
\langle W(C)\rangle\sim e^{-\sigma\operatorname{Area}(C)}
$$

implies, for a large rectangle,

$$
V(R)\sim \sigma R.
$$

This is the standard confinement diagnostic in pure gauge theory.

A perimeter law,

$$
\langle W(C)\rangle\sim e^{-\mu\operatorname{Perimeter}(C)},
$$

often indicates screening or a Higgs-like behavior, depending on the theory and on the line operator considered.

The caveat is crucial: in the presence of dynamical matter charged under the center, a fundamental Wilson loop may fail as a strict order parameter because the string can break. Then one must use more refined diagnostics: asymptotic string breaking, higher-form symmetry, allowed genuine lines, center symmetry, spectra, and other line operators.

## ’t Hooft loops and disorder operators

A Wilson loop inserts an electric probe. An ’t Hooft loop inserts a magnetic disorder probe. Roughly, an ’t Hooft line $T(C)$ is defined by requiring a prescribed magnetic singularity or gauge-bundle modification around the curve $C$.

This definition sounds less elementary than the Wilson-loop trace because disorder operators are not always expressible as simple polynomials or exponentials of the local fields. That is precisely why they are valuable. They can diagnose phases that are invisible in local elementary variables.

The Wilson–’t Hooft logic is:

| Operator | Probe | Typical diagnostic |
|---|---|---|
| Wilson loop $W(C)$ | electric external charge | confinement or screening of electric charges |
| ’t Hooft loop $T(C)$ | magnetic external charge | magnetic confinement, Higgs behavior, dual superconductivity |
| Wilson–’t Hooft line | electric and magnetic charge | dyonic phases and line-operator spectrum |

The exact labels of these operators depend on the global form of the gauge group, not only on the Lie algebra. For example, gauge theories with the same local algebra can differ in which Wilson or ’t Hooft lines are genuine. This is one reason modern discussions of confinement emphasize line operators and one-form symmetries.

## Polyakov loops and thermal probes

At finite temperature $T_{\mathrm{phys}}=1/\beta$, the Euclidean time direction is a circle of circumference $\beta$. The Polyakov loop in representation $R$ is

$$
P_R(\mathbf x)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P
\exp\left(-i\int_0^\beta d\tau\,A_\tau(\tau,\mathbf x)\right).
$$

In pure gauge theory, the expectation value of a fundamental Polyakov loop is related to the free energy $F_q$ of an isolated static test quark:

$$
\langle P(\mathbf x)\rangle\sim e^{-\beta F_q}.
$$

If center symmetry is unbroken, $\langle P\rangle=0$ and the isolated test charge has infinite free energy in the thermodynamic limit. If center symmetry is broken, $\langle P\rangle\neq0$ and the theory is deconfined in this diagnostic.

With dynamical fundamental matter, center symmetry is explicitly broken and the Polyakov loop is no longer an exact order parameter. It can still be a useful diagnostic of crossover behavior, but its interpretation is weaker.

Thermal observables also include the free-energy density

$$
f(T)=-\frac{T}{V_{\mathrm{space}}}\log Z(T),
$$

screening masses from spatial correlators, susceptibilities, transport coefficients, and real-time spectral functions. Many of these are nonperturbative because thermal infrared physics can be strongly coupled even when short-distance modes are perturbative.

## Generalized symmetries and extended observables

Ordinary global symmetries act on local operators and particle states. Higher-form global symmetries act on extended operators and extended charged objects. A $q$-form symmetry has charged operators supported on $q$-dimensional submanifolds. Thus a one-form symmetry acts naturally on line operators such as Wilson loops.

This language reorganizes older confinement diagnostics. In pure $SU(N)$ Yang–Mills theory, the center symmetry can be understood as a one-form symmetry acting on Wilson loops. Whether this symmetry is unbroken or broken is reflected in the large-loop behavior of charged line operators.

This is more than vocabulary. It forces the diagnostic to match the charged objects. A local operator cannot carry charge under a pure one-form symmetry. Therefore a phase distinguished by a one-form symmetry cannot be diagnosed by a local order parameter alone.

The same idea extends to surface operators, domain walls, topological defects, and non-invertible defects. The general rule is:

$$
\text{the support dimension of the observable should match the symmetry or defect it probes.}
$$

Modern treatments of phases increasingly phrase order parameters, anomalies, dualities, and selection rules in this extended-operator language.

## Partition functions as observables

The partition function itself can be an observable once the spacetime manifold and background fields are specified:

$$
Z[M;B,\theta,\ldots].
$$

Here $M$ is the spacetime manifold, $B$ denotes background fields for global symmetries, and $\theta$ denotes topological angles or other global parameters. This object can detect anomalies, topological response, theta dependence, symmetry-protected phases, finite-temperature transitions, and global aspects of gauge theory.

For a theory with topological sectors labeled by $Q$,

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q.
$$

The theta-dependent free-energy density is

$$
F(\theta)=-\frac{1}{V}\log Z(\theta),
$$

and the topological susceptibility is

$$
\chi_t=\left.\frac{\partial^2F}{\partial\theta^2}\right|_{\theta=0}
=\frac{1}{V}\left(\langle Q^2\rangle-\langle Q\rangle^2\right)_{\theta=0}.
$$

When CP symmetry implies $\langle Q\rangle=0$ at $\theta=0$, this becomes

$$
\chi_t=\frac{\langle Q^2\rangle}{V}.
$$

This is a model example of a nonperturbative observable: it depends on sector sums that are invisible in ordinary perturbation theory around $Q=0$.

## Disorder, twists, and boundary conditions

A disorder operator is often defined by changing boundary conditions or imposing a singularity rather than by inserting a local function of fields. The classic examples are twist operators in spin systems, vortex operators in scalar or gauge theories, and ’t Hooft operators in gauge theory.

This may feel strange at first. But path integrals are perfectly capable of defining observables by conditions. For example, an interface or defect operator may be specified by saying how fields behave when crossing a codimension-one surface. A vortex operator may be specified by the winding of fields around its insertion. A symmetry-twist defect may be specified by a transition function across a cut.

The advantage is that disorder operators often see the dual variables of a problem. In a phase where the original order parameter is disordered, the disorder parameter may be ordered. This is one reason nonperturbative QFT constantly moves between operators and boundary conditions.

## Entanglement and geometric diagnostics

Entanglement observables are also nonperturbative diagnostics, though they require special care because they are ultraviolet sensitive. For a spatial region $A$, the entanglement entropy is

$$
S_A=-\operatorname{Tr}\rho_A\log\rho_A,
$$

where $\rho_A$ is the reduced density matrix. In continuum QFT, $S_A$ usually has cutoff-dependent area-law terms. Nevertheless, universal pieces can diagnose central charges, topological order, RG monotonicity, edge modes, and boundary conditions in suitable settings.

Replica methods define related quantities using partition functions on branched manifolds:

$$
S_A=-\left.\frac{\partial}{\partial n}\log\operatorname{Tr}\rho_A^n\right|_{n=1}.
$$

This places entanglement in the same broad family as geometric partition-function observables. The main caveat is that regulator dependence must be separated from universal information.

## How to choose the observable

The choice of observable should be driven by the phenomenon, not by habit.

| Phenomenon | Good first observables | Main caveat |
|---|---|---|
| Mass gap | exponential decay of connected correlators, finite-volume spectrum | operator must overlap with the lightest state in the channel |
| Confinement in pure gauge theory | large Wilson loops, center one-form symmetry, flux-tube spectrum | dynamical matter can screen fundamental charges |
| Deconfinement | Polyakov loop, center symmetry, thermal free energy | Polyakov loop is not exact with dynamical fundamental matter |
| Spontaneous symmetry breaking | sourced order parameter, Goldstone correlators | infinite-volume and zero-source limits must be ordered |
| Theta dependence | $Z(\theta)$, topological susceptibility, sector-resolved observables | depends on global definition and boundary conditions |
| Topological phase | ground-state degeneracy, line/surface operators, $Z[M]$, entanglement constants | local correlators may look trivial |
| Dual phases | disorder operators, vortices, soliton operators | operator dictionary may be nonlocal |
| Strongly coupled spectrum | finite-volume energies, spectral functions, lattice correlators | continuum and volume extrapolations are essential |
| Generalized symmetry realization | charged extended operators | support dimension and genuine-operator data matter |

A useful repair habit is to ask: “What would have to behave differently in two phases?” Then choose an observable that directly measures that behavior.

## Gauge invariance and physical meaning

Gauge invariance is not a decorative constraint. It is the difference between a variable and an observable.

The gauge potential $A_\mu$ is a useful variable. A gluon propagator in a fixed gauge can be useful for calculations and diagnostics. But by itself it is not a gauge-invariant physical observable. A Wilson loop, a glueball correlator such as

$$
\langle \operatorname{tr}F_{\mu\nu}F_{\mu\nu}(x)\,\operatorname{tr}F_{\rho\sigma}F_{\rho\sigma}(0)\rangle,
$$

or a finite-volume energy level is closer to the physical Hilbert-space question.

This does not mean gauge-fixed correlators are worthless. They can be useful inside a method, especially when combined with Ward identities, BRST symmetry, or a fixed computational scheme. The point is that nonperturbative claims about phases and spectra should ultimately be phrased in gauge-invariant or gauge-fixed-but-carefully-defined terms.

## The order of limits is part of the observable

Many nonperturbative observables are really limits of regulated observables. The order matters.

For spontaneous symmetry breaking,

$$
\lim_{J\to0}\lim_{V\to\infty}\langle\mathcal O\rangle_J
$$

can differ from

$$
\lim_{V\to\infty}\lim_{J\to0}\langle\mathcal O\rangle_J.
$$

For Wilson loops, the confinement diagnostic involves a large-loop limit. For rectangular loops, one usually takes

$$
T\to\infty
$$

first to extract a potential $V(R)$, then studies large $R$. For lattice calculations, one must take continuum, infinite-volume, and statistical limits. For thermal transitions, one must distinguish finite-volume crossovers from thermodynamic singularities.

A nonperturbative observable is therefore not just an expression. It is an expression plus a limiting procedure.

## Common pitfalls

### Using gauge-variant fields as phase diagnostics without qualification

A gauge-fixed propagator may be useful, but a phase statement should be phrased in gauge-invariant observables, global symmetries, spectra, or carefully defined gauge-fixed criteria.

### Expecting every phase to have a local order parameter

Topological phases, confinement with screening, generalized-symmetry phases, and dual phases may not be distinguished by local one-point functions.

### Forgetting dynamical screening

A Wilson-loop area law for fundamental external charges is a sharp diagnostic in pure gauge theory. With dynamical fundamental matter, strings can break, so the same loop is no longer a strict order parameter.

### Treating a condensate as automatically physical

Composite condensates may be scheme-dependent, regulator-dependent, or mixed with lower-dimension operators. Their physical content often lies in symmetry realization, Ward identities, or relations among observables.

### Ignoring global form of the gauge group

The Lie algebra does not determine the full set of line operators. The global form of the gauge group and the allowed genuine lines are part of the theory.

### Calling $Z$ “just normalization”

The partition function on a specified manifold with specified backgrounds is often a physical observable. It can detect anomalies, theta dependence, thermal transitions, and topological response.

### Comparing phases at finite volume only

Some phase distinctions become sharp only after the thermodynamic limit. Finite-volume spectra are valuable, but their large-volume behavior must be interpreted carefully.

## Relations to other pages

This page completes the conceptual entrance formed by [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/), [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/), and [Semiclassical versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/).

Later chapters will specialize these observables: mass-gap diagnostics, Wilson-loop diagnostics, ’t Hooft-loop diagnostics, Polyakov-loop diagnostics, topological susceptibility, lattice observables, finite-volume spectra, instanton-induced correlation functions, and generalized-symmetry diagnostics.

## Research status

- **Established:** Gauge-invariant local correlators and finite-volume spectra are fundamental nonperturbative observables for masses, gaps, and bound states.
- **Established:** Wilson loops, Polyakov loops, and ’t Hooft loops are central diagnostics of confinement, screening, and thermal deconfinement, with important caveats when dynamical matter screens external charges.
- **Established:** Partition functions with specified manifolds, background fields, spin structures, and theta angles encode anomalies, topological response, and sector sums.
- **Caveat:** No single observable diagnoses every phase. Local order parameters, extended operators, entanglement, spectra, and background-field responses are complementary.
- **Active:** The modern theory of generalized symmetries, non-invertible defects, categorical symmetries, and global forms of gauge theories continues to refine the classification of phases and the meaning of line and defect operators.

## Exercises

### Exercise 1: Spectral decomposition of a Euclidean correlator

Let $\mathcal O$ be a Hermitian operator in a finite-volume quantum theory with Hamiltonian $H$. Show that

$$
C(\tau)=\langle0|\mathcal O(\tau)\mathcal O(0)|0\rangle-\langle0|\mathcal O|0\rangle^2
$$

can be written as

$$
C(\tau)=\sum_{n\neq0}|\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)\tau}.
$$

<details>
<summary><strong>Solution</strong></summary>

In Euclidean time,

$$
\mathcal O(\tau)=e^{H\tau}\mathcal O e^{-H\tau}.
$$

Insert a complete set of energy eigenstates,

$$
1=\sum_n |n\rangle\langle n|,
\qquad
H|n\rangle=E_n|n\rangle.
$$

Then

$$
\langle0|\mathcal O(\tau)\mathcal O(0)|0\rangle
=\sum_n\langle0|e^{H\tau}\mathcal O e^{-H\tau}|n\rangle\langle n|\mathcal O|0\rangle.
$$

Since $\langle0|e^{H\tau}=e^{E_0\tau}\langle0|$ and $e^{-H\tau}|n\rangle=e^{-E_n\tau}|n\rangle$, this becomes

$$
\sum_n e^{-(E_n-E_0)\tau}|\langle0|\mathcal O|n\rangle|^2.
$$

The $n=0$ term is $|\langle0|\mathcal O|0\rangle|^2$, which is removed by subtracting the disconnected piece. Hence

$$
C(\tau)=\sum_{n\neq0}|\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)\tau}.
$$

</details>

### Exercise 2: Area law and a linear potential

Suppose a large rectangular Wilson loop of spatial size $R$ and Euclidean time size $T$ obeys

$$
\langle W(R,T)\rangle\sim e^{-\sigma RT}
$$

for large $R,T$. Using

$$
\langle W(R,T)\rangle\sim e^{-T V(R)}
$$

at large $T$, show that $V(R)\sim\sigma R$.

<details>
<summary><strong>Solution</strong></summary>

Compare the two exponential forms:

$$
e^{-T V(R)}\sim e^{-\sigma R T}.
$$

For large $T$, the exponents must match at leading order, so

$$
V(R)\sim \sigma R.
$$

Thus an area law for a rectangular Wilson loop corresponds to a linearly rising static potential, with string tension $\sigma$.

</details>

### Exercise 3: Why the source limit matters

Let $\mathcal O$ be odd under an exact $\mathbb Z_2$ symmetry. Explain why $\langle\mathcal O\rangle=0$ at finite volume and zero source, even if the infinite-volume theory has a broken phase.

<details>
<summary><strong>Solution</strong></summary>

At finite volume, the path integral or trace sums over configurations related by the exact $\mathbb Z_2$ symmetry. Since $\mathcal O$ is odd, each configuration and its symmetry partner contribute equal and opposite values to the expectation value. Therefore

$$
\langle\mathcal O\rangle=0
$$

at zero source.

To select one broken vacuum, introduce a source $J\mathcal O$, take the infinite-volume limit first, and only then send $J\to0$:

$$
\langle\mathcal O\rangle_{\mathrm{SSB}}
=\lim_{J\to0}\lim_{V\to\infty}\langle\mathcal O\rangle_J.
$$

The infinite-volume limit suppresses tunneling or averaging between the broken vacua, allowing a nonzero order parameter.

</details>

### Exercise 4: Topological susceptibility from theta dependence

Suppose

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q,
\qquad
F(\theta)=-\frac{1}{V}\log Z(\theta).
$$

Show that

$$
\left.\frac{\partial^2F}{\partial\theta^2}\right|_{\theta=0}
=\frac{1}{V}\left(\langle Q^2\rangle-\langle Q\rangle^2\right)_{\theta=0}.
$$

<details>
<summary><strong>Solution</strong></summary>

First compute

$$
\frac{\partial\log Z}{\partial\theta}
=\frac{1}{Z}\sum_Q iQ e^{i\theta Q}Z_Q
=i\langle Q\rangle_\theta.
$$

Then

$$
\frac{\partial^2\log Z}{\partial\theta^2}
=\frac{1}{Z}\sum_Q (-Q^2)e^{i\theta Q}Z_Q
-\left(\frac{1}{Z}\sum_Q iQe^{i\theta Q}Z_Q\right)^2.
$$

This is

$$
\frac{\partial^2\log Z}{\partial\theta^2}
=-\langle Q^2\rangle_\theta+\langle Q\rangle_\theta^2.
$$

Since $F=-(1/V)\log Z$,

$$
\frac{\partial^2F}{\partial\theta^2}
=\frac{1}{V}\left(\langle Q^2\rangle_\theta-\langle Q\rangle_\theta^2\right).
$$

Evaluating at $\theta=0$ gives the stated result.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, especially the chapters on the Lehmann–Källén representation, Wilson loops, lattice theory, confinement, solitons, monopoles, instantons, and theta vacua.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong-coupling expansion, confinement criteria, topology of gauge fields, loop dynamics, and large N.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, 2nd ed., for phases of gauge theories, solitons, vortices, monopoles, instantons, anomalies, confinement, and higher-form symmetries.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the modern language of higher-form symmetries, charged extended operators, background fields, and anomalies.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., for Euclidean functional integrals, correlation functions, RG, critical phenomena, and nonperturbative field-theoretic methods.
- H. Casini and M. Huerta, “Entanglement Entropy in Free Quantum Field Theory,” for Euclidean and real-time methods for entanglement entropy in QFT.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for order/disorder variables, gauge-theory diagnostics, topological phases, and condensed-matter applications of QFT observables.

## Version history

- **2026-06-25:** Initial polished draft. Added observable map, phase-diagnostic table, spectral-decomposition exercise, Wilson-loop area-law exercise, source-limit exercise, and theta-susceptibility exercise.
