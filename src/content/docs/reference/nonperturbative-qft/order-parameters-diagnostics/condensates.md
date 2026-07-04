---
title: "Condensates"
description: "Explains scalar, chiral, and gauge-invariant condensates as renormalized composite-operator expectation values and phase diagnostics in nonperturbative QFT."
sidebar:
  label: "Condensates"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman; Zinn-Justin; Srednicki; Schwartz; Shifman; Fradkin; Altland–Simons."
topics:
  - condensates
  - composite operators
  - vacuum expectation values
  - chiral symmetry breaking
  - operator renormalization
  - Banks-Casher relation
  - order parameters
canonicalTopics:
  - nonperturbative-qft
  - condensates
  - order-parameters
  - composite-operators
  - chiral-symmetry-breaking
researchStatus:
  established:
    - "Condensates are standard nonperturbative diagnostics when they are defined as renormalized expectation values of physical operators in a specified state and limiting procedure."
  active:
    - "For gauge theories and strongly coupled systems, the numerical value and even the interpretation of some condensates can depend on renormalization scheme, regulator, operator basis, and separation from perturbative contributions."
---

## Summary

A **condensate** is the expectation value of a field-theoretic operator in a state, usually the vacuum or a thermal state. The word is most useful when the operator is composite and the expectation value carries nonperturbative information:

$$
\langle \mathcal O\rangle\neq 0.
$$

Typical examples include a scalar condensate $\langle\phi\rangle$, a chiral condensate $\langle\bar\psi\psi\rangle$, and gauge-invariant gluonic condensates such as $\langle F_{\mu\nu}^aF^{a\mu\nu}\rangle$ after renormalization and convention choices.

Condensates are not literal substances filling the vacuum. They are expectation values of operators, and all the usual questions apply: Which operator? Which state? Which regulator? Which renormalization scheme? Which source limit? Which symmetry is being tested?

The clean diagnostic statement is:

$$
\text{a condensate is a renormalized composite-operator VEV with a specified physical interpretation.}
$$

That precise sentence is what keeps the physics honest.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A flow diagram showing how a bare composite operator becomes a renormalized condensate diagnostic after subtraction, source selection, and interpretation.](/figures/nonperturbative-qft/condensate-renormalization-map.svg)

<figcaption>

A condensate is not just a formal symbol $\langle\mathcal O\rangle$. To use it as a phase diagnostic, one must specify the composite operator, renormalize and subtract it, choose the state by a source or boundary condition, take the thermodynamic and continuum limits, and then interpret the result in terms of symmetry, spectrum, or response.

</figcaption>
</figure>

## Prerequisites

You should know [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/), [Local Order Parameters](/nonperturbative-qft/order-parameters-diagnostics/local-order-parameters/), and [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/).

It also helps to know the Euclidean path integral, source-dependent generating functionals, and the basic fact that products of fields at the same point require renormalization.

## Core idea

A condensate is a one-point function,

$$
\langle\mathcal O(x)\rangle,
$$

but in QFT this simple notation hides three layers.

First, $\mathcal O$ may be a **composite operator**. Even if the elementary fields are well regulated, products such as $\phi^2(x)$, $\bar\psi\psi(x)$, and $F_{\mu\nu}F^{\mu\nu}(x)$ have short-distance singularities. The operator must be defined by a regulator and renormalization prescription.

Second, the expectation value is **state-dependent**. A symmetric finite-volume ground state may give zero even when infinite-volume pure phases have nonzero order parameters. Conversely, an explicitly symmetry-breaking source may induce a condensate that disappears when the source is removed in the right order.

Third, a condensate is only a **diagnostic** after one says what it diagnoses. For example:

| Condensate | Typical diagnostic role | Main caveat |
|---|---|---|
| $\langle\phi\rangle$ | Broken ordinary global symmetry in a scalar theory. | If $\phi$ is gauge variant, this is not a physical order parameter. |
| $\langle\bar\psi\psi\rangle$ | Chiral symmetry breaking and dynamical mass generation. | Depends on quark masses, regulator, and renormalization scheme. |
| $\langle\phi^2\rangle$ | Fluctuation strength or density-like observable. | Often has additive power divergences. |
| $\langle F^2\rangle$ | Gauge-invariant vacuum structure and trace-anomaly physics. | Separation into perturbative and nonperturbative pieces is scheme-dependent. |
| $\langle\mathcal O\rangle_T$ | Thermal phase diagnostic or response coefficient. | Thermal expectation values mix vacuum and medium contributions. |

The most useful mental model is that a condensate is a **local measurement of the state**. It can be decisive, but only if the measurement is well defined.

## Setup and conventions

We use the conventions of [Conventions and Notation](/nonperturbative-qft/conventions/). In Euclidean signature, let

$$
Z[J]=\int \mathcal D\Phi\,\exp\left[-S_E[\Phi]+\int d^d x\,J(x)\mathcal O_R(x)\right],
$$

where $\mathcal O_R$ is a renormalized operator. Then

$$
\langle\mathcal O_R(x)\rangle_J
=\frac{\delta\log Z[J]}{\delta J(x)}.
$$

At $J=0$, this gives the one-point function in the state selected by the path integral and boundary conditions. If several pure phases exist, one often defines a phase-specific condensate by adding a small source, taking the thermodynamic limit, and then removing the source:

$$
\langle\mathcal O_R\rangle_{\alpha}
=\lim_{J\to 0_\alpha}\lim_{\mathcal V\to\infty}
\frac{\delta\log Z[J]}{\delta J(x)}.
$$

The subscript $\alpha$ labels the direction in source space or the pure phase selected by boundary conditions. The order of limits is part of the definition, not optional bookkeeping.

For a parameter $\lambda$ appearing in the Euclidean action as

$$
S_E(\lambda)=S_E(0)+\lambda\int d^d x\,\mathcal O(x),
$$

the free-energy density

$$
f(\lambda)=-\frac{1}{\mathcal V}\log Z(\lambda)
$$

obeys

$$
\frac{\partial f}{\partial\lambda}
=\frac{1}{\mathcal V}\left\langle \int d^d x\,\mathcal O(x)\right\rangle
=\langle\mathcal O\rangle,
$$

for a translation-invariant state, up to the sign convention chosen for how $\lambda$ enters $S_E$. This is the Euclidean version of the Feynman–Hellmann idea: condensates are derivatives of vacuum or thermal energy with respect to couplings.

## Composite operators and renormalization

A local product of fields at the same spacetime point is not automatically a finite operator. The general renormalization pattern is

$$
\mathcal O_i^R(\mu)
=Z_{ij}(\mu,\Lambda)\mathcal O_j^B(\Lambda)+c_i(\mu,\Lambda)\mathbf 1,
$$

where $\Lambda$ is a regulator scale, $\mu$ is a renormalization scale, and operators with the same quantum numbers can mix. The identity term is important because one-point functions are sensitive to vacuum-energy-like subtractions.

For example, in a free scalar theory,

$$
\langle\phi^2(x)\rangle
=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}
$$

is UV divergent for $d\ge 2$. This does not mean that $\phi^2$ is meaningless. It means that the bare expression is not yet the renormalized local operator. One may define a normal-ordered operator, a minimally subtracted operator, or a lattice-subtracted operator. These definitions differ by local counterterms.

The diagnostic value of a condensate therefore lies not in the unrenormalized number but in a well-defined comparison:

$$
\langle\mathcal O_R\rangle_{\text{phase A}}
\quad\text{versus}\quad
\langle\mathcal O_R\rangle_{\text{phase B}},
$$

or in a response relation such as

$$
\frac{\partial f}{\partial\lambda}=\langle\mathcal O_R\rangle.
$$

A useful rule of thumb:

:::note[Diagnostic rule]
A condensate used as an order parameter should either be protected by symmetry, expressed as a derivative of a physical quantity, or stated with its renormalization scheme and scale.
:::

## Scalar condensates

Consider a real scalar theory with a $\mathbb Z_2$ symmetry,

$$
\phi\mapsto -\phi.
$$

A local order parameter for breaking this symmetry is

$$
\langle\phi\rangle.
$$

In finite volume and with symmetric boundary conditions, the exact ground state need not choose either sign, so

$$
\langle\phi\rangle=0
$$

can coexist with long-distance order. The pure-phase definition uses a source $h$:

$$
\langle\phi\rangle_{\pm}
=\lim_{h\to 0^{\pm}}\lim_{\mathcal V\to\infty}\langle\phi\rangle_h.
$$

The square

$$
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle
$$

also detects long-range order, even if the finite-volume one-point function vanishes. This is why condensates and correlation functions should be read together.

A different scalar condensate is

$$
\langle\phi^2\rangle.
$$

This is even under $\mathbb Z_2$, so it is not an order parameter for $\mathbb Z_2$ breaking. It measures fluctuation strength and responds to the mass parameter. If the Euclidean action contains

$$
S_E\supset \int d^d x\,\frac{1}{2}m^2\phi^2,
$$

then

$$
\frac{\partial f}{\partial m^2}=\frac{1}{2}\langle\phi^2\rangle.
$$

Because $\phi^2$ is composite, the right-hand side must be interpreted after renormalization. The lesson is small but important: a nonzero condensate is not automatically an order parameter. It depends on the operator's symmetry quantum numbers.

## Chiral condensates

In a theory of Dirac fermions, the bilinear

$$
\bar\psi\psi
$$

is a central condensate. In QCD-like theories with light quarks, a nonzero chiral condensate indicates spontaneous breaking of chiral symmetry. For $N_f$ massless Dirac fermions in a vectorlike gauge theory, the classical global symmetry is schematically

$$
SU(N_f)_L\times SU(N_f)_R\times U(1)_V,
$$

ignoring the anomalous axial $U(1)$ factor. The condensate

$$
\langle\bar\psi\psi\rangle
=\langle\bar\psi_L\psi_R+\bar\psi_R\psi_L\rangle
$$

is not invariant under independent left and right flavor rotations. A nonzero value selects the diagonal subgroup,

$$
SU(N_f)_L\times SU(N_f)_R\longrightarrow SU(N_f)_V,
$$

and implies Goldstone modes when the symmetry is exact.

With a fermion mass term in Euclidean signature,

$$
S_E\supset \int d^d x\,m\bar\psi\psi,
$$

the condensate is a derivative of the partition function:

$$
\langle\bar\psi\psi\rangle_m
=-\frac{1}{\mathcal V}\frac{\partial\log Z}{\partial m}.
$$

The sign follows from the convention that the mass appears in $S_E$ and $Z=e^{-S_E}$. Some authors define the positive chiral order parameter as

$$
\Sigma=-\lim_{m\to0}\langle\bar\psi\psi\rangle_m.
$$

The thermodynamic limit comes first:

$$
\Sigma
=-\lim_{m\to0^+}\lim_{\mathcal V\to\infty}\langle\bar\psi\psi\rangle_m.
$$

Taking $m\to0$ first at finite volume can erase the order parameter, just as in the scalar example.

## Banks–Casher relation

The chiral condensate has a beautiful spectral interpretation. In a Euclidean gauge background, let the massless Dirac operator have eigenvalues

$$
D_E\psi_n=i\lambda_n\psi_n,
$$

with real $\lambda_n$ for the anti-Hermitian convention. Define the spectral density per unit volume near zero by

$$
\rho_D(\lambda)
=\frac{1}{\mathcal V}\left\langle\sum_n\delta(\lambda-\lambda_n)\right\rangle.
$$

Then, in a QCD-like theory with the usual assumptions and the limits taken in the correct order,

$$
\Sigma=\pi\rho_D(0).
$$

This is the Banks–Casher relation. It says that chiral symmetry breaking is equivalent to an accumulation of near-zero Dirac eigenvalues in the infinite-volume limit.

The order of limits matters again. At finite volume, the Dirac spectrum is discrete, and $\rho_D(0)$ is not a smooth thermodynamic density. Chiral symmetry breaking appears when eigenvalues pile up near the origin with spacing of order $1/\mathcal V$.

The relation is an archetype of nonperturbative QFT: a symmetry-breaking condensate is detected through spectral data of an operator in fluctuating gauge backgrounds. Perturbative Feynman diagrams around the trivial vacuum are not the natural language for this phenomenon.

## Gauge-invariant condensates

Gauge theory adds a sharp warning: gauge-variant condensates are not physical order parameters. A statement such as

$$
\langle A_\mu^aA^{a\mu}\rangle\neq0
$$

in a fixed gauge may be useful in a particular formalism, but it is not by itself a gauge-invariant phase statement.

Physical condensates in gauge theory should be gauge invariant or phrased as responses of gauge-invariant observables. Examples include

$$
\left\langle \bar\psi\psi\right\rangle,
\qquad
\left\langle F_{\mu\nu}^aF^{a\mu\nu}\right\rangle,
\qquad
\left\langle F_{\mu\nu}^a\widetilde F^{a\mu\nu}\right\rangle,
$$

when these are renormalized and interpreted in a definite scheme. In QCD phenomenology one often discusses a gluon condensate, but its numerical value is not a regulator-independent observable in the same way as a mass ratio or an S-matrix element. It appears naturally in operator product expansions and trace-anomaly relations, where the scheme and subtraction convention are part of the setup.

The trace anomaly gives a useful example. In a four-dimensional Yang–Mills theory, the trace of the stress tensor has the schematic form

$$
T^\mu_{\ \mu}
=\frac{\beta(g)}{2g^3}F_{\mu\nu}^aF^{a\mu\nu}
+\sum_f m_f(1+\gamma_m)\bar\psi_f\psi_f,
$$

up to convention-dependent normalizations and improvement terms. Taking a vacuum expectation value relates the vacuum energy to condensates:

$$
\langle T^\mu_{\ \mu}\rangle=d\,\epsilon_{\text{vac}}
$$

in $d$ spacetime dimensions for a Lorentz-invariant vacuum. The combination entering the stress tensor is physical; individual condensates require the stated renormalization convention.

## Condensates at finite temperature

At finite temperature, expectation values are thermal:

$$
\langle\mathcal O\rangle_T
=\frac{1}{Z(\beta)}\operatorname{Tr}\left(e^{-\beta H}\mathcal O\right),
\qquad \beta=1/T.
$$

A condensate can then diagnose a thermal transition or crossover. For example, the chiral condensate in QCD-like theories decreases as temperature increases and is used to diagnose chiral restoration. In pure Yang–Mills theory, however, deconfinement is more directly diagnosed by center symmetry and the Polyakov loop, not by a local scalar condensate.

Thermal condensates often contain a vacuum part plus a medium-dependent part. When comparing phases, one should say whether the vacuum contribution has been subtracted:

$$
\Delta\langle\mathcal O\rangle_T
=\langle\mathcal O\rangle_T-\langle\mathcal O\rangle_{T=0}.
$$

This subtraction is especially important for composite operators with UV divergences. The ultraviolet divergence is local and usually temperature independent; the finite thermal change is often better behaved.

## Condensates and the operator product expansion

Condensates often appear in the operator product expansion. For two local operators at short Euclidean separation,

$$
\mathcal A(x)\mathcal B(0)
\sim \sum_i C_i(x,\mu)\mathcal O_i(0;\mu),
$$

so taking a vacuum expectation value gives

$$
\langle\mathcal A(x)\mathcal B(0)\rangle
\sim \sum_i C_i(x,\mu)\langle\mathcal O_i(\mu)\rangle.
$$

This formula separates short-distance coefficients from long-distance matrix elements. It is one of the most important bridges between perturbative and nonperturbative physics.

But the separation is not unique. Changing the scheme or operator basis changes the coefficients and condensates together while leaving the full correlator unchanged. So an OPE condensate should not be treated as an isolated directly measurable number. Its meaning is tied to the expansion and scheme in which it appears.

## Diagnostic workflow

When using a condensate as a nonperturbative diagnostic, run this checklist.

| Step | Question | Good practice |
|---:|---|---|
| 1 | What is the operator? | Specify quantum numbers and whether it is local, composite, and gauge invariant. |
| 2 | How is it renormalized? | State the scheme, scale, and possible operator mixing. |
| 3 | What state is used? | Specify vacuum, thermal state, finite-volume state, or source-selected pure phase. |
| 4 | What limits are taken? | State the order of source, mass, volume, and continuum limits. |
| 5 | What does it diagnose? | Connect the nonzero value to symmetry, response, spectrum, or phase structure. |
| 6 | What are the caveats? | Separate physical statements from convention-dependent numerical values. |

A condensate without this information is like a scattering amplitude without external states. It might be suggestive, but it is not yet a well-posed observable.

## Common pitfalls

**Calling every VEV a condensate.** The term is usually reserved for expectation values with physical diagnostic content, especially composite or symmetry-sensitive ones. A one-point function becomes useful only after its role is stated.

**Ignoring source limits.** A condensate that diagnoses spontaneous symmetry breaking usually requires the thermodynamic limit before the symmetry-breaking source is removed.

**Using gauge-variant VEVs as physical order parameters.** Gauge fixing can be a useful calculational device, but physical phases must be distinguished by gauge-invariant observables, global symmetries, line operators, spectra, or response.

**Forgetting additive renormalization.** Operators such as $\phi^2$ and $F^2$ can mix with the identity. Their bare VEVs can contain large cutoff-dependent pieces.

**Treating the chiral condensate as a number without a scheme.** $\langle\bar\psi\psi\rangle$ depends on renormalization scale and scheme, although its symmetry-breaking role and relations to physical quantities are meaningful.

**Confusing condensates with confinement.** Chiral symmetry breaking and confinement often coexist in QCD-like theories, but they are logically distinct. A chiral condensate is not a definition of confinement.

**Confusing an OPE parameter with an independent observable.** Condensates in an OPE depend on how short- and long-distance physics are separated.

## Relations to other pages

- [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/) explains one-point functions and source selection in more general terms.
- [Local Order Parameters](/nonperturbative-qft/order-parameters-diagnostics/local-order-parameters/) explains how local VEVs diagnose symmetry realization.
- [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/) shows how two-point functions encode poles, thresholds, and continua.
- [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) explains how correlators reveal the lowest energy scale in a channel.
- Later pages on **Chiral Symmetry Breaking**, **QCD as Strongly Coupled QFT**, and **Schwinger–Dyson Equations** will use condensates as central examples.

## Research status

- **Established:** Condensates defined as renormalized composite-operator expectation values are standard tools in QFT, statistical mechanics, lattice field theory, and QCD phenomenology.
- **Established:** Chiral condensates diagnose spontaneous chiral symmetry breaking in QCD-like theories, with the Banks–Casher relation connecting them to near-zero Dirac eigenvalues under standard assumptions.
- **Convention-dependent:** The numerical value of a composite-operator condensate usually depends on renormalization scheme and scale.
- **Subtle:** Gauge-variant condensates can be useful in a fixed gauge but do not by themselves define gauge-invariant phases.
- **Active:** Extracting, subtracting, and interpreting condensates in strongly coupled gauge theories, finite-temperature systems, and OPE-based phenomenology can require careful nonperturbative input.

## Exercises

### Exercise 1: Source derivative for a condensate

Let

$$
Z[J]=\int\mathcal D\Phi\,e^{-S_E[\Phi]+\int d^d x\,J\mathcal O}.
$$

Show that, for constant $J$ and translation-invariant states,

$$
\frac{1}{\mathcal V}\frac{\partial\log Z}{\partial J}=\langle\mathcal O\rangle_J.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate under the integral:

$$
\frac{\partial Z}{\partial J}
=\int\mathcal D\Phi\left(\int d^d x\,\mathcal O(x)\right)
e^{-S_E+J\int d^d x\,\mathcal O}.
$$

Therefore

$$
\frac{\partial\log Z}{\partial J}
=\left\langle\int d^d x\,\mathcal O(x)\right\rangle_J.
$$

If the state is translation invariant,

$$
\left\langle\int d^d x\,\mathcal O(x)\right\rangle_J
=\mathcal V\langle\mathcal O\rangle_J,
$$

which gives the result.

</details>

### Exercise 2: Why $\langle\phi^2\rangle$ is not a $\mathbb Z_2$ order parameter

A scalar theory is invariant under $\phi\mapsto-\phi$. Explain why $\langle\phi\rangle$ can diagnose spontaneous breaking of this symmetry, while $\langle\phi^2\rangle$ cannot distinguish the two broken vacua.

<details>
<summary><strong>Solution</strong></summary>

Under the symmetry,

$$
\phi\mapsto-\phi,
\qquad
\phi^2\mapsto\phi^2.
$$

Thus $\langle\phi\rangle$ changes sign between the two pure broken phases, while $\langle\phi^2\rangle$ is the same in both. A nonzero $\langle\phi^2\rangle$ can measure fluctuation strength or response to $m^2$, but it does not identify which $\mathbb Z_2$-related vacuum has been selected.

</details>

### Exercise 3: Mass derivative and the chiral condensate

For Euclidean fermions with

$$
S_E(m)=S_E(0)+m\int d^d x\,\bar\psi\psi,
$$

show that

$$
\langle\bar\psi\psi\rangle_m
=-\frac{1}{\mathcal V}\frac{\partial\log Z}{\partial m}.
$$

<details>
<summary><strong>Solution</strong></summary>

Since $Z=\int e^{-S_E(m)}$,

$$
\frac{\partial Z}{\partial m}
=-\int\mathcal D\Phi\left(\int d^d x\,\bar\psi\psi\right)e^{-S_E(m)}.
$$

Dividing by $Z$ gives

$$
\frac{\partial\log Z}{\partial m}
=-\left\langle\int d^d x\,\bar\psi\psi\right\rangle_m.
$$

Translation invariance gives

$$
\left\langle\int d^d x\,\bar\psi\psi\right\rangle_m
=\mathcal V\langle\bar\psi\psi\rangle_m,
$$

so

$$
\langle\bar\psi\psi\rangle_m
=-\frac{1}{\mathcal V}\frac{\partial\log Z}{\partial m}.
$$

</details>

### Exercise 4: Interpreting the Banks–Casher relation

Suppose the low-lying Dirac eigenvalues in a sequence of finite boxes have typical spacing proportional to $1/\mathcal V$ near $\lambda=0$. What does this suggest about $\rho_D(0)$ and the chiral condensate in the infinite-volume limit?

<details>
<summary><strong>Solution</strong></summary>

If the spacing near zero scales as $1/\mathcal V$, then the number of eigenvalues in a fixed small interval around zero grows proportionally to $\mathcal V$. The density per unit volume,

$$
\rho_D(\lambda)=\frac{1}{\mathcal V}\left\langle\sum_n\delta(\lambda-\lambda_n)\right\rangle,
$$

can then approach a nonzero limit at $\lambda=0$. By Banks–Casher,

$$
\Sigma=\pi\rho_D(0),
$$

so a nonzero $\rho_D(0)$ indicates a nonzero chiral condensate, assuming the usual infinite-volume and chiral limits are taken in the correct order.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on spontaneous symmetry breaking, effective potentials, currents, and functional methods.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for order parameters, field integrals, renormalization, and critical phenomena.
- M. Srednicki, *Quantum Field Theory*, for vacuum expectation values, chiral symmetry breaking, Wilson loops, lattice theory, and anomalies.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for path-integral definitions, vacuum expectation values, operator renormalization, and spectral decomposition.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for chiral condensates, phases of gauge theories, the ’t Hooft model, anomalies, and confinement examples.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for order parameters, dualities, gauge-theory phases, and topological phases.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for broken symmetry, collective phenomena, response functions, and condensed-matter uses of condensates.

## Version history

- **2026-06-26:** Initial polished draft.
