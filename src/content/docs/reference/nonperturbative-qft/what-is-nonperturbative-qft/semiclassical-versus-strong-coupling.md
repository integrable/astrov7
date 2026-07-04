---
title: "Semiclassical versus Strong Coupling"
description: "A precise distinction between semiclassical nonperturbative effects, strong coupling in chosen variables, and controlled strong-coupling expansions."
sidebar:
  label: "Semiclassical vs Strong Coupling"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman; Polyakov; Mariño; Shifman; Zinn-Justin; Wilson–Kogut."
topics:
  - semiclassical methods
  - strong coupling
  - instantons
  - lattice strong-coupling expansion
  - dual variables
canonicalTopics:
  - nonperturbative-qft
  - semiclassical-methods
  - strong-coupling
  - instantons
  - lattice-field-theory
researchStatus:
  established:
    - "Semiclassical nonperturbative effects can be weakly coupled and exponentially small, while strong coupling is a statement about the size of a parameter in a chosen description."
  active:
    - "Finding controlled variables for strongly coupled real-time, finite-density, and four-dimensional gauge-theory dynamics remains a central research problem."
---

## Summary

“Nonperturbative” and “strongly coupled” are related words, but they are not synonyms. This page separates three different ideas that are often bundled together:

| Phrase | What it literally says | Typical mathematical form |
|---|---|---|
| Perturbative | Expand around one chosen saddle or solvable theory. | $\sum_n a_n g^n$ |
| Semiclassical nonperturbative | Include additional saddles whose action is large in the small parameter. | $e^{-A/g^2}\sum_n b_n g^n$ |
| Strongly coupled | The coupling in the chosen variables is not small at the scale of interest. | no reliable small-$g$ expansion |

A weakly coupled instanton calculation can be nonperturbative. A strong-coupling lattice expansion can be perturbative in a different parameter. A strongly coupled continuum theory may become weakly coupled after a duality, a large-N limit, a change of variables, or a change of observable. The trouble begins when these cases are collapsed into one phrase: “nonperturbative = impossible.” That is exactly the wrong moral.

The central distinction is:

$$
\text{semiclassical control is about a large saddle action;}
\qquad
\text{strong coupling is about bad small-fluctuation variables.}
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![Map of semiclassical and strong-coupling regimes](/figures/nonperturbative-qft/semiclassical-strong-coupling-map.svg)

<figcaption>

Coupling size and expansion type are independent axes. Weak coupling can still have nonperturbative saddle sectors. Strong coupling can sometimes be organized by a strong-coupling expansion, dual variables, large-N methods, or a regulator-defined continuum limit.

</figcaption>
</figure>

## Prerequisites

You should know the conceptual distinction in [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/), the role of asymptotic series in [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/), and the Euclidean conventions fixed in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

This page is still conceptual. Later chapters make each kind of control concrete: saddle-point expansion, instantons, lattice strong-coupling expansions, large-N limits, and exact low-dimensional models.

## Core idea

A semiclassical expansion is an expansion around a saddle point when a small parameter multiplies quantum fluctuations. A typical Euclidean path integral has the form

$$
Z(g)=\int\mathcal D\Phi\,\exp\left[-\frac{1}{g^2}S[\Phi]\right].
$$

A saddle $\Phi_\alpha$ obeys

$$
\left.\frac{\delta S}{\delta\Phi}\right|_{\Phi_\alpha}=0,
$$

and its contribution has the schematic form

$$
Z_\alpha(g)\sim
\exp\left[-\frac{S[\Phi_\alpha]}{g^2}\right]
\sum_{n\geq0}c_{\alpha,n}g^n.
$$

If $g\ll1$, the fluctuation series around each isolated saddle can be controlled. But if $\Phi_\alpha$ is not the perturbative saddle, its contribution is still nonperturbative in the ordinary expansion around the perturbative saddle, because the factor $e^{-S[\Phi_\alpha]/g^2}$ has zero Taylor expansion at $g=0$.

Strong coupling is a different statement. It says that the coupling in the variables currently being used is not small. In a gauge theory, for example, the running coupling may become large in the infrared. Then an expansion around weakly coupled gluons is no longer controlled. But “no small coupling in these variables” is not the same as “no calculation exists.” The theory may have a lattice definition, a dual description, a large-N expansion, a bootstrap formulation, an effective long-distance description, or exact constraints from symmetry and topology.

A first-pass diagnostic is:

$$
\begin{array}{ccl}
\text{semiclassical} &\Rightarrow& \text{small fluctuations around known saddles},\\
\text{strongly coupled} &\Rightarrow& \text{small fluctuations in chosen variables are not reliable},\\
\text{nonperturbative} &\Rightarrow& \text{not captured by finite ordinary expansion around one saddle}.
\end{array}
$$

These arrows are not reversible.

## Setup and conventions

This page uses Euclidean notation. A semiclassical normalization means that the action is written as

$$
S_E[\Phi;g]=\frac{1}{g^2}S_0[\Phi]+S_1[\Phi]+O(g^2),
$$

or, more schematically,

$$
S_E\sim \frac{1}{g^2}S_{\mathrm{cl}}.
$$

The saddle expansion is then an expansion in powers of $g$ or $g^2$ around each saddle. In gauge theory, the instanton normalization used throughout this volume is

$$
S_{\mathrm{inst}}=\frac{8\pi^2}{g^2}
$$

for a charge-one Yang–Mills instanton, so the semiclassical weight is

$$
e^{-8\pi^2/g^2+i\theta}.
$$

For lattice gauge theory, the bare lattice coupling is often traded for

$$
\beta=\frac{2N}{g_0^2}
$$

in pure $SU(N)$ Yang–Mills theory with the Wilson action. The strong-coupling limit $g_0\to\infty$ is the small-$\beta$ limit. Thus a “strong-coupling expansion” is usually a power series in a parameter such as $\beta$, not a weak-coupling loop expansion in $g_0$.

The same word “coupling” can therefore appear in opposite-looking ways depending on the expansion being used. That is not a contradiction; it is a warning label.

## Three axes that should not be confused

The cleanest mental model has three axes.

### Axis 1: Which saddle or sector?

A perturbative expansion around one saddle gives one local series:

$$
Z_{0}(g)\sim \sum_{n\geq0}a_n g^{2n}.
$$

The full answer may require other sectors:

$$
Z(g)\sim \sum_\alpha
\exp\left[-\frac{S_\alpha}{g^2}\right]
\sum_{n\geq0}a_{\alpha,n}g^n.
$$

The label $\alpha$ may denote instanton number, flux sector, winding number, vacuum, boundary condition, or a more general saddle. If the ordinary perturbative sector is $\alpha=0$, the sectors with $S_\alpha>0$ are invisible in every finite order of the $\alpha=0$ expansion.

### Axis 2: Is the expansion parameter small?

Weak coupling means a chosen parameter is small. In a semiclassical gauge-theory problem, this may mean $g^2\ll1$, making the instanton action large and the instanton gas dilute in favorable regimes. In perturbative scattering, it may mean the running coupling at the momentum transfer is small.

Strong coupling means the chosen coupling is not small. But the chosen coupling is not sacred. It depends on variables, scheme, scale, and sometimes duality frame.

### Axis 3: Is there an organizing principle?

A calculation can be controlled without being a weak-coupling Feynman-diagram expansion. Examples include:

| Organizing principle | Small parameter or control | Typical use |
|---|---|---|
| Semiclassics | $g^2$, $\hbar$, large action | tunneling, instantons, solitons, false-vacuum decay |
| Lattice strong coupling | $\beta\sim1/g_0^2$, hopping parameter | area laws, qualitative phase structure |
| Large N | $1/N$ | factorization, saddle equations, planar dominance |
| Dual variables | dual weak coupling or local variables | vortices, solitons, order/disorder maps, electric–magnetic descriptions |
| Symmetry and anomaly constraints | exact selection rules | phase constraints, matching, forbidden flows |
| Integrability or exact solvability | infinite conserved charges, algebraic data | spectra and S-matrices in special low-dimensional models |
| Numerical continuum methods | controlled cutoffs, finite-volume/basis extrapolations | spectra, matrix elements, thermal quantities |

A good page or paper should say which organizing principle is being used. “Nonperturbative” is not enough information.

## Semiclassical physics is not the same as perturbative physics

Semiclassical physics still uses expansions. The difference is that the expansion is performed around every relevant saddle, not only around the perturbative one.

Consider a Euclidean action normalized as

$$
S_E[q]=\frac{1}{\hbar}\int d\tau\left[\frac12\dot q^2+V(q)\right].
$$

A classical Euclidean solution $q_\star(\tau)$ contributes

$$
\exp\left[-\frac{S_0[q_\star]}{\hbar}\right]
\times
\left(\det{}' K\right)^{-1/2}
\times
\left(\text{zero-mode and interaction factors}\right),
$$

where $K$ is the quadratic fluctuation operator around the saddle. The determinant and zero-mode factors are part of ordinary semiclassical bookkeeping. The nonperturbative feature is the exponential weight.

In a double-well potential, the instanton connecting the two minima gives an exponentially small splitting of energy levels,

$$
\Delta E\propto e^{-S_{\mathrm{inst}}/\hbar}.
$$

The splitting is small when $S_{\mathrm{inst}}/\hbar\gg1$. That is exactly when the calculation is controlled. So the standard example of a nonperturbative effect is not a messy, uncontrolled strong-coupling phenomenon; it is a clean weak-semiclassical phenomenon.

The same pattern appears in four-dimensional Yang–Mills theory. In a regime where instantons are dilute and the coupling at the instanton scale is small, a one-instanton sector contributes

$$
e^{-8\pi^2/g^2+i\theta}\times(\text{determinants, zero modes, collective coordinates}).
$$

The contribution is nonperturbative in $g$, but the fluctuation calculation may be perturbative around the instanton saddle.

:::note[Loop expansion versus saddle expansion]
A loop expansion around one saddle is perturbation theory. A saddle expansion that includes several disconnected sectors is semiclassical nonperturbative physics. Both use small parameters, but they answer different questions.
:::

## Strong coupling is a statement about chosen variables

A theory is strongly coupled when the variables you are using no longer provide a small-fluctuation expansion. This wording matters.

In asymptotically free gauge theory, the running coupling satisfies, at one loop,

$$
\mu\frac{dg}{d\mu}=-b_0g^3,
\qquad b_0>0.
$$

At short distances, $g(\mu)$ is small and quarks and gluons can be useful perturbative variables for suitable observables. At distances of order $\Lambda^{-1}$, the coupling is large, and the weakly coupled quark–gluon expansion fails for the spectrum. But the physical statement is not “the theory becomes meaningless.” The statement is that a particular expansion becomes meaningless.

The long-distance description may involve hadrons, glueballs, flux tubes, chiral Lagrangians, topological fields, or no weakly coupled quasiparticle variables at all. Which description is appropriate depends on the observable.

This is why one often says “strong coupling in the ultraviolet variables.” The phrase keeps the door open for a better infrared description.

## Strong-coupling expansions are still expansions

The phrase “strong-coupling expansion” sounds paradoxical only if perturbation theory is equated with small $g$. On a lattice, strong-coupling expansions are often ordinary power series in a parameter that is small when the original coupling is large.

For pure $SU(N)$ lattice gauge theory with Wilson action,

$$
S_W=\beta\sum_p\left(1-\frac1N\operatorname{Re}\operatorname{Tr}U_p\right),
\qquad
\beta=\frac{2N}{g_0^2},
$$

the strong-coupling regime $g_0\gg1$ is the small-$\beta$ regime. Expanding $e^{-S_W}$ in powers of $\beta$ and integrating link variables exactly produces a controlled expansion at sufficiently small $\beta$.

For a large Wilson loop $C$, the leading nonzero contribution comes from tiling the minimal surface bounded by $C$ with plaquettes. The schematic result is

$$
\langle W(C)\rangle
\sim
\left[c\,\beta+O(\beta^2)\right]^{A(C)/a^2}
=
\exp\left[-\sigma_{\mathrm{lat}}A(C)+\cdots\right],
$$

where $A(C)$ is the minimal lattice area and $c$ is a group-dependent constant. This is an area law at strong bare coupling.

This is a real nonperturbative calculation: it is gauge-invariant, regulator-defined, and invisible to the weak-coupling loop expansion around $A_\mu=0$. But it is also an expansion. Its caveat is different: the strong-coupling region of a lattice theory may or may not be analytically connected to the continuum limit of interest. The expansion teaches an important mechanism and gives exact statements in its domain, but the continuum extrapolation is another question.

## Strong coupling may be weak coupling in disguise

Sometimes strong coupling in one set of variables is weak coupling in another. This is the great recurring trick of theoretical physics.

A duality can trade elementary excitations for solitons, order operators for disorder operators, electric variables for magnetic variables, particles for vortices, or a local Lagrangian for a completely different description. In two-dimensional statistical systems, order–disorder dualities make this lesson concrete. In two-dimensional QFT, bosonization can turn a strongly interacting fermionic description into a bosonic one, or vice versa. In supersymmetric gauge theories, holomorphy and duality can give exact information far beyond naive perturbation theory. In special large-N systems, a strongly coupled field theory may have a weakly curved gravitational dual.

The conservative lesson is not that every strongly coupled theory has a known weakly coupled dual. Most do not. The lesson is that “strong coupling” is not an invariant property of nature by itself. It is a property of a description.

A better diagnostic is:

$$
\text{What are the observables, symmetries, states, and variables in which the question is simple?}
$$

This question is less glamorous than saying “duality,” but it is more useful.

## Examples that separate the ideas

### Weak and perturbative: short-distance QCD observables

At large momentum transfer $Q\gg\Lambda_{\mathrm{QCD}}$, asymptotic freedom makes the strong coupling small. Certain inclusive observables can be organized using perturbation theory, factorization, and RG evolution. Nonperturbative input may still enter through parton distributions or condensates, but the short-distance coefficient functions are perturbative.

This is weak coupling and perturbative control.

### Weak and nonperturbative: instantons

A Yang–Mills instanton has action

$$
S_{\mathrm{inst}}=\frac{8\pi^2}{g^2}.
$$

At small $g$, this action is large, so the instanton contribution is exponentially suppressed:

$$
e^{-8\pi^2/g^2}\ll1.
$$

The effect is weakly coupled and nonperturbative. It is weakly coupled because fluctuations around the saddle can be organized. It is nonperturbative because no finite power series in $g$ around the trivial sector produces it.

### Strongly coupled but expandable: lattice strong coupling

In lattice gauge theory at small $\beta$, the expansion parameter is $\beta$, not $g_0$. Since $\beta=2N/g_0^2$, this is an expansion around large bare coupling. It can produce an area law for Wilson loops in its domain.

This is strong coupling and perturbative-in-a-different-variable control.

### Strongly coupled with no known small parameter: infrared QCD spectrum

The light hadron spectrum in real-world QCD is not obtained by simply adding more gluon loops around the perturbative vacuum. Lattice QCD, chiral effective theory, large-N arguments, sum rules, and phenomenological models all provide windows, but there is no universally simple small parameter for all questions.

This is strongly coupled nonperturbative physics in the practical sense.

### Strongly coupled but constrained: conformal field theories

Many conformal field theories do not have a known weakly coupled Lagrangian description. Yet their data are constrained by unitarity, symmetry, crossing, operator product expansion, and sometimes supersymmetry. The conformal bootstrap can treat such theories without expanding around a Gaussian action.

This is nonperturbative in a definition-and-observable sense, even when no literal coupling constant is present.

## What semiclassical control requires

A semiclassical calculation is not automatically trustworthy. It needs conditions.

First, one needs a saddle or family of saddles. The equation

$$
\delta S_E=0
$$

must have solutions satisfying the relevant boundary conditions. A guessed field configuration is not a saddle calculation.

Second, the fluctuation operator should be understood. Around a saddle $\Phi_\star$,

$$
S_E[\Phi_\star+\eta]
=S_E[\Phi_\star]+\frac12\int\eta K\eta+\cdots.
$$

Zero modes require collective coordinates. Negative modes signal instabilities or tunneling rates rather than ordinary stable contributions. Gauge redundancies require gauge fixing and ghosts. Fermion zero modes imply selection rules and may force certain correlators to vanish unless enough fermionic insertions are included.

Third, the saddle expansion should be parametrically controlled. A single instanton calculation usually assumes that multi-instanton effects are suppressed, interactions between saddles are manageable, and large-size or small-size regions of moduli space do not destroy the approximation.

Fourth, one must know what observable is being computed. A saddle that dominates one observable may be irrelevant to another.

A disciplined semiclassical result therefore says:

$$
\text{saddles} + \text{zero modes} + \text{determinants} + \text{domain of validity}.
$$

Leaving out the last item is how beautiful formulas become folklore.

## What strong-coupling control requires

A strong-coupling calculation also needs conditions.

For a lattice expansion, one needs a finite regulator and convergence or at least a controlled domain in the bare parameters. One then asks whether the result survives toward a continuum limit. A strong-coupling area law at small $\beta$ is not automatically a proof of confinement in the continuum Yang–Mills theory, because the continuum limit may lie at a different part of parameter space.

For a large-N expansion, one needs a well-defined scaling limit. In gauge theory this is usually the ’t Hooft limit

$$
N\to\infty,
\qquad
\lambda=g^2N\quad\text{fixed}.
$$

The expansion may control planar diagrams and factorization, but effects of order $e^{-N}$ or phase transitions in the large-N saddle can still matter.

For a duality, one needs a precise map of observables, symmetries, parameters, and global data. It is not enough to say “the dual theory is weakly coupled.” Which line operators are genuine? Which background fields are turned on? Which anomalies match? Which Hilbert spaces are identified?

For numerical methods, one needs continuum, infinite-volume, truncation, and statistical error control. A numerical answer is nonperturbative only to the extent that its regulator and extrapolations are under control.

## Why the distinction matters for learning

Many students learn perturbative QFT first. That is sensible: free fields, Wick contractions, Feynman diagrams, renormalization, and the S-matrix are the grammar of much of the subject. The danger is that the first grammar can masquerade as the whole language.

When nonperturbative physics appears, the student often hears three messages at once:

1. perturbation theory diverges;
2. instantons are exponentially small;
3. QCD is strongly coupled in the infrared.

These are all true in their proper contexts, but they explain different failures of naive perturbation theory. Divergence is about the large-order behavior of a series. Instantons are about additional saddles. Infrared QCD is about the wrong variables and the long-distance physical spectrum.

Separating these issues makes the subject less mystical. It also makes it easier to choose tools:

| If the problem involves... | First tool to try |
|---|---|
| exponentially small tunneling | semiclassical saddles |
| factorial growth and ambiguities | Borel analysis and resurgence |
| confinement diagnostics | Wilson loops, center symmetry, lattice, line operators |
| a mass gap | spectral correlators, finite-volume spectra, lattice, Hamiltonian methods |
| strong coupling in one variable | dual variables, large N, bootstrap, EFT, lattice |
| phase distinction | order/disorder parameters and long-distance limits |
| topology or theta dependence | sector sums, background fields, anomalies |

The table is not a recipe book. It is triage.

## Common pitfalls

### Saying “instantons are strong-coupling effects”

Instantons often require weak coupling for calculability. They are nonperturbative because their weights are exponential in $-1/g^2$, not because $g$ is large.

### Saying “strong coupling means no expansion”

A strong-coupling expansion is an expansion around a strong-coupling limit, often in an inverse coupling or lattice parameter. It may be perfectly controlled in its domain.

### Trusting a semiclassical saddle without checking zero modes

Zero modes are not optional normalization details. They encode collective coordinates, symmetries, volume factors, and selection rules. Fermion zero modes can determine which correlation functions receive an instanton contribution.

### Treating a strong-coupling lattice result as automatically continuum

A lattice strong-coupling result is a statement about a region of bare-parameter space. Whether it controls the desired continuum theory requires a continuum-limit argument.

### Treating coupling size as invariant

The value of a coupling depends on scale, scheme, and variables. Physical statements should be phrased in terms of observables, spectra, symmetries, and correlation functions.

### Confusing “not perturbative in elementary fields” with “not describable”

A theory may be nonperturbative in one set of fields while having an effective description in terms of different fields. Chiral perturbation theory is not a weak expansion in quarks and gluons; it is an expansion in pion fields and momenta.

### Assuming strong coupling is always the interesting limit

Some of the deepest nonperturbative information appears at weak coupling, precisely because weak coupling lets us calculate exponentially small effects cleanly.

## Relations to other pages

This page refines the slogan from [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/). The previous page, [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/), explains why exponential factors are invisible to ordinary power series. The next conceptual page, [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/), explains why choosing the correct observable is often more important than choosing the most familiar field variable.

Later pages on saddle-point expansion, instantons in quantum mechanics, strong-coupling expansion on the lattice, Wilson-loop diagnostics, large-N vector models, and confinement mechanisms will turn the distinctions here into calculations.

## Research status

- **Established:** Semiclassical contributions such as instantons and tunneling amplitudes are nonperturbative in the ordinary loop expansion but can be controlled at weak coupling in suitable regimes.
- **Established:** Strong-coupling expansions, especially on the lattice, are genuine expansions in parameters adapted to the strong-coupling regime.
- **Established:** Strong coupling is description-dependent. Dualities, effective theories, large-N limits, and exact methods can reorganize a problem that is strongly coupled in its original variables.
- **Caveat:** A strong-coupling expansion at finite lattice spacing is not automatically a continuum result. The continuum limit must be analyzed separately.
- **Active:** General controlled methods for strongly coupled four-dimensional real-time dynamics, finite-density QFT, and many non-supersymmetric continuum gauge theories remain major open research areas.

## Exercises

### Exercise 1: Weakly coupled but nonperturbative

Let

$$
F(g)=g^2+3g^4+C e^{-A/g^2},
\qquad A>0.
$$

Explain why the last term is nonperturbative in $g$ even when $g\ll1$.

<details>
<summary><strong>Solution</strong></summary>

For $g\ll1$, the term $e^{-A/g^2}$ is very small. But nonperturbative does not mean large; it means invisible to the ordinary power series in $g$.

The function $e^{-A/g^2}$ has zero Taylor expansion at $g=0$. Therefore no finite-order expansion in powers of $g$ can determine the coefficient $C$. The term is weakly coupled in the sense that it is exponentially suppressed, but it is nonperturbative in the expansion parameter.

</details>

### Exercise 2: Strong coupling as a small-parameter expansion

In pure $SU(N)$ lattice gauge theory with Wilson action, the conventional lattice parameter is

$$
\beta=\frac{2N}{g_0^2}.
$$

What happens to $\beta$ in the strong bare-coupling limit $g_0\to\infty$? Why can this lead to an expansion?

<details>
<summary><strong>Solution</strong></summary>

If $g_0\to\infty$, then

$$
\beta=\frac{2N}{g_0^2}\to0.
$$

The Boltzmann factor for the Wilson action can be expanded in powers of $\beta$. The resulting series is called a strong-coupling expansion because it is an expansion around large $g_0$, but its actual small parameter is $\beta$. This is why “strong coupling” does not automatically mean “no perturbative expansion of any kind.”

</details>

### Exercise 3: Identifying the type of nonperturbative statement

Classify each statement as primarily perturbative, semiclassical nonperturbative, strong-coupling, or definition-level nonperturbative.

1. Computing a one-loop beta function.
2. Computing a tunneling splitting proportional to $e^{-S_0/\hbar}$.
3. Extracting the glueball spectrum from Euclidean lattice correlators.
4. Showing that a formal continuum path integral is the limit of a reflection-positive lattice theory.

<details>
<summary><strong>Solution</strong></summary>

1. A one-loop beta function is perturbative: it is a coefficient in an expansion around a weakly coupled description.
2. A tunneling splitting proportional to $e^{-S_0/\hbar}$ is semiclassical nonperturbative: it is controlled by a saddle but invisible in the ordinary power series around one minimum.
3. The glueball spectrum from Euclidean lattice correlators is strongly coupled nonperturbative physics computed with a regulator-defined method.
4. A continuum path integral constructed as a reflection-positive lattice limit is definition-level nonperturbative: it concerns the existence and Hilbert-space meaning of the theory, not merely a coefficient in an expansion.

</details>

### Exercise 4: Why a duality changes the meaning of strong coupling

Suppose two descriptions of the same physics use couplings $g$ and $\widetilde g$ with the schematic relation

$$
\widetilde g\sim \frac{1}{g}.
$$

Explain why a theory that is strongly coupled in the $g$ variables may be weakly coupled in the $\widetilde g$ variables. What must still be checked before using the dual description?

<details>
<summary><strong>Solution</strong></summary>

If $g\gg1$, then $\widetilde g\sim1/g\ll1$. A weak expansion in $\widetilde g$ may therefore describe physics that is strongly coupled in the original variables.

However, one must check that the two descriptions really define the same theory and that the observable of interest is mapped correctly. This includes matching symmetries, spectra or operator data, background fields, global forms of gauge groups when relevant, line operators, anomalies, and parameter ranges. A dual weak coupling is useful only after the dictionary is under control.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on instantons, false-vacuum decay, solitons, and large N.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong-coupling expansion, instantons, confinement criteria, topology of gauge fields, loop dynamics, and large N.
- M. Mariño, *Instantons and Large N*, for instantons, large-order behavior, Borel summability, Yang–Mills instantons, renormalons, and large-N methods.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, 2nd ed., for phases of gauge theories, solitons, instantons, false-vacuum decay, anomalies, and confinement in lower-dimensional models.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., for Euclidean field integrals, RG, instantons, large-order behavior, and critical phenomena.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” *Physics Reports* **12** (1974), for the Wilsonian viewpoint on critical phenomena, QFT, and exact RG ideas.

## Version history

- **2026-06-25:** Initial polished draft. Added distinction map, examples separating weak semiclassical physics from strong coupling, and exercises on instanton weights, lattice strong-coupling parameters, and dual variables.
