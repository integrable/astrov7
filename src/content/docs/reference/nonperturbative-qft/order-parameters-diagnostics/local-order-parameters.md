---
title: "Local Order Parameters"
description: "Local order parameters diagnose ordinary symmetry realization through source-selected expectation values, long-distance correlators, and response functions."
sidebar:
  label: "Local Order Parameters"
  order: 1
level: Graduate
status: "Polished draft"
source: "Zinn-Justin; Coleman; Weinberg; Srednicki; Schwartz; Burgess; Fradkin; Altland–Simons."
topics:
  - local order parameters
  - spontaneous symmetry breaking
  - vacuum expectation values
  - cluster decomposition
  - susceptibility
  - Landau theory
canonicalTopics:
  - nonperturbative-qft
  - order-parameters
  - spontaneous-symmetry-breaking
  - phase-diagnostics
researchStatus:
  established:
    - "Local gauge-invariant expectation values and their long-distance correlators are standard diagnostics for ordinary symmetry-breaking phases."
  active:
    - "In gauge theories with matter, topological phases, finite-density systems, and strongly coupled continuum limits, local order parameters may be incomplete or scheme-dependent diagnostics."
---

## Summary

A **local order parameter** is a local operator whose expectation value, correlation function, or response to a source distinguishes phases. In the simplest Landau examples it is a field such as the Ising magnetization, a scalar condensate, or a staggered spin density. In relativistic QFT it should be a well-defined renormalized local operator, and if it is meant to diagnose a physical phase without gauge fixing, it must be gauge invariant.

The most important definition is not merely

$$
\langle \mathcal O\rangle \neq 0.
$$

It is the source-selected, thermodynamic-limit statement

$$
v_{\hat h}
=
\lim_{h\to 0^+}\lim_{L\to\infty}
\langle \mathcal O_{\hat h}(0)\rangle_{L,h},
$$

where $h\mathcal O_{\hat h}$ is a small symmetry-breaking source and $L$ is the linear size of the system. The order of limits is part of the physics. At finite volume, the exact ground state or Euclidean path integral often restores the symmetry by averaging over would-be broken vacua.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A source selects one of two phases before the thermodynamic limit is taken; removing the source too early gives a symmetric average.](/figures/nonperturbative-qft/local-order-parameter-source-limits.svg)

<figcaption>

A local order parameter for spontaneous symmetry breaking is defined by a limiting prescription. A tiny source selects a pure phase; then the thermodynamic limit is taken; only afterward is the source removed. Reversing the order gives the symmetric finite-volume average.

</figcaption>
</figure>

Local order parameters are powerful because they turn a qualitative claim about a vacuum into a computable statement about an operator. They are also dangerous because zero, nonzero, gauge-variant, finite-volume, and scheme-dependent expectation values are easy to misread. This page is the repair manual.

## Prerequisites

You should know [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/), [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/), and [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/). The finite-volume and source limits use the language of [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/). The effective-potential caveats are explained in [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/).

## Core idea

A phase is not just a Lagrangian. A phase is a realization of the theory in a state, sector, and limiting procedure. A local order parameter is one of the simplest tools for recognizing that realization.

Suppose a theory has a global symmetry group $G$ and a local operator $\mathcal O_a(x)$ transforming in some representation of $G$. If the vacuum expectation value

$$
v_a=\langle\Omega|\mathcal O_a(0)|\Omega\rangle
$$

is nonzero in a pure phase and is not invariant under all of $G$, then the vacuum preserves only the subgroup

$$
H=\{g\in G: R(g)_a{}^b v_b=v_a\}.
$$

The pattern

$$
G\longrightarrow H
$$

is then visible in a local observable. This is the basic Landau picture.

The same idea also works without saying “field value.” One may diagnose the phase by the large-distance behavior of a two-point function:

$$
\lim_{|x|\to\infty}\langle \mathcal O_a(x)\mathcal O_b(0)\rangle
=v_a v_b
$$

in a pure translation-invariant phase, up to the usual qualifications about indices, conjugation, and connected components. This correlator formulation is often more robust because it does not hide finite-volume averaging.

The local order-parameter viewpoint is therefore a three-part package:

| Ingredient | Meaning |
|---|---|
| Operator | Choose a local, renormalized, physically meaningful $\mathcal O(x)$. |
| State or source | Specify the vacuum, pure phase, ensemble, and source limit. |
| Long-distance test | Use VEVs, cluster limits, susceptibilities, or finite-size scaling. |

When all three pieces are explicit, local order parameters are sharp. When one is missing, the words “the order parameter vanishes” are often just fog with equations in it.

## Setup and conventions

Work in Euclidean signature unless stated otherwise. Put the theory in a finite spatial box of linear size $L$ and volume $V_{d-1}=L^{d-1}$, with an infrared regulator chosen so that the partition function is well-defined. Let $\mathcal O_a(x)$ be a local composite operator. Its renormalized definition may depend on a scale $\mu$ and a scheme.

Introduce a source $J^a(x)$ through

$$
Z[J]
=
\int \mathcal D\phi\,
\exp\left[-S_E[\phi]+\int d^d x\,J^a(x)\mathcal O_a(x)\right].
$$

The connected generating functional is

$$
W[J]=\log Z[J].
$$

The source-dependent expectation value is

$$
\langle\mathcal O_a(x)\rangle_J
=
\frac{\delta W[J]}{\delta J^a(x)}.
$$

For a constant source $J^a=h\hat h^a$, define

$$
\mathcal O_{\hat h}=\hat h^a\mathcal O_a.
$$

The source direction $\hat h$ is a physical part of the limiting prescription. In an $O(N)$-symmetric model, for example, $\hat h$ chooses a direction in order-parameter space. Different choices related by the exact symmetry describe equivalent pure phases, but the exact finite-volume average over all directions gives zero.

For a diagnostic of a physical phase, $\mathcal O$ should be invariant under gauge redundancy. Gauge fixing can be useful for calculations and intuition, but a gauge-variant local field VEV is not by itself a physical order parameter.

## Definition

A **local order parameter** for an ordinary symmetry-breaking phase is a local operator $\mathcal O_a(x)$ such that:

1. $\mathcal O_a$ transforms nontrivially under a global symmetry or under another physical transformation being tested;
2. in at least one pure phase,

   $$
   v_a=\lim_{h\to0}\lim_{L\to\infty}\langle\mathcal O_a(0)\rangle_{L,h}
   $$

   is nonzero or takes a phase-distinguishing value;
3. the stabilizer of $v_a$ gives the unbroken subgroup, or the set of possible $v_a$ labels distinct ordinary phases;
4. the statement survives renormalization and limiting-procedure checks.

The word “ordinary” matters. Topological phases, confinement with screening, gauge-Higgs continuity, and phases distinguished by line operators may not admit any local order parameter even though they are physically distinct.

A local order parameter can be scalar, vector, tensor, spinorial, matrix-valued, or charged under internal symmetries, but a translation-invariant Lorentz-invariant vacuum can only have nonzero expectation values for operators compatible with the unbroken spacetime symmetries. For example, a Lorentz-invariant vacuum may have a scalar condensate, but not a nonzero expectation value of a vector current unless Lorentz invariance is broken.

## Source limits and pure phases

The finite-volume trap is the first thing to get right.

Take a theory with a $\mathbb Z_2$ symmetry and an operator $\phi(x)$ odd under it. In infinite volume the symmetry may be spontaneously broken, with two pure phases $|+\rangle$ and $|-\rangle$ satisfying

$$
\langle +|\phi|+\rangle=v,
\qquad
\langle -|\phi|-\rangle=-v.
$$

But in a finite box with no external source, the exact ground state is usually a symmetric or antisymmetric linear combination. Then

$$
\langle\phi\rangle_{L,h=0}=0.
$$

This does not prove the symmetry is unbroken. It proves that finite volume is doing its job: tunneling, mixing, or ensemble averaging has not yet been suppressed.

The broken-phase order parameter is obtained by

$$
\langle\phi\rangle_+
=
\lim_{h\to0^+}\lim_{L\to\infty}\langle\phi\rangle_{L,h}.
$$

The reverse order gives

$$
\lim_{L\to\infty}\lim_{h\to0}\langle\phi\rangle_{L,h}=0
$$

if the $h\to0$ limit is taken symmetrically at finite $L$. This is why spontaneous symmetry breaking is an infrared phenomenon. It is not captured by simply asking whether a finite-dimensional Hamiltonian has a symmetry-invariant ground state.

For continuous symmetries the same issue is even sharper. The order parameter direction lives on a vacuum manifold $G/H$, and finite volume restores the symmetry by averaging over that manifold. The source picks one point on it.

## Long-range order and cluster tests

The VEV test is concise, but the correlator test is often better.

Define the connected correlator

$$
C_{ab}(x)
=
\langle\mathcal O_a(x)\mathcal O_b(0)\rangle
-
\langle\mathcal O_a\rangle\langle\mathcal O_b\rangle.
$$

In a massive pure phase, $C_{ab}(x)$ usually decays exponentially at large Euclidean separation,

$$
C_{ab}(x)\sim e^{-|x|/\xi},
$$

up to powers of $|x|$ and matrix structure. The length $\xi$ is the correlation length in that channel.

Long-range order appears in the full two-point function as

$$
\lim_{|x|\to\infty}
\langle\mathcal O_a(x)\mathcal O_b(0)\rangle
=v_a v_b.
$$

This statement is a version of cluster decomposition in a pure phase. It also gives a practical finite-volume diagnostic: if $\langle\mathcal O\rangle$ vanishes by symmetry in a finite box, the large-distance correlator can still reveal a plateau approaching $|v|^2$ as $L\to\infty$.

For an Ising-like scalar, one often estimates

$$
v^2
=\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle
$$

inside the broken phase. For a vector order parameter, one uses the appropriate invariant contraction. For matrix order parameters, one examines eigenvalues, invariant traces, or the transformation pattern under left and right symmetries.

## Susceptibility and response

An order parameter is also a response coefficient. If $h$ is a source for $\mathcal O$, the susceptibility is

$$
\chi
=\left.\frac{\partial\langle\mathcal O\rangle_h}{\partial h}\right|_{h=0}
=
\int d^d x\,\langle\mathcal O(x)\mathcal O(0)\rangle_c,
$$

assuming translation invariance and ignoring finite-volume normalization details. A diverging susceptibility signals that the system is very easy to polarize in the $\mathcal O$ channel. Near a continuous transition this divergence is one of the standard ways to see criticality.

The susceptibility is often more stable than a raw VEV because it can be measured in the symmetric phase. For example, above a magnetic critical temperature the magnetization vanishes but the magnetic susceptibility grows as the transition is approached. In QFT language, the two-point function develops a long correlation length and the integral over spacetime becomes large.

The same logic applies to explicit symmetry breaking. If the source is not removable because the microscopic theory contains a small symmetry-breaking parameter, then the order parameter may never vanish sharply. One then studies response and scaling rather than a strict phase distinction.

## Landau example

The fastest clean example is a single real scalar with effective potential

$$
V(\phi)=\frac{r}{2}\phi^2+\frac{u}{4}\phi^4-h\phi,
\qquad u>0.
$$

The $h=0$ theory has a $\mathbb Z_2$ symmetry $\phi\mapsto-\phi$. The stationary equation is

$$
r\phi+u\phi^3-h=0.
$$

At $h=0$:

- for $r>0$, the minimum is at $\phi=0$ and the symmetry is unbroken;
- for $r<0$, the minima are

  $$
  \phi=\pm \sqrt{\frac{-r}{u}},
  $$

  and the source $h$ selects one sign.

Thus, in mean-field language,

$$
v_\pm=\pm\sqrt{\frac{-r}{u}}.
$$

This example should be taken as a conceptual model, not as a proof that real QFT phase transitions are always mean-field. Fluctuations can change exponents, move phase boundaries, generate anomalous dimensions, or even prevent long-range order in low dimensions. The order-parameter idea survives; the naive potential need not.

The mass of small fluctuations in the symmetric phase is approximately

$$
m^2=r,
$$

while in the broken phase it is approximately

$$
m_\sigma^2=-2r
$$

for the radial mode in this simple one-component example. In a continuous-symmetry version, the directions tangent to the vacuum manifold give Goldstone modes when the symmetry is global and the assumptions of Goldstone's theorem apply.

## Standard examples

| Theory or system | Local order parameter | What it diagnoses | Caveat |
|---|---|---|---|
| Ising universality class | $\phi$ or spin field $\sigma$ | Breaking of $\mathbb Z_2$ symmetry. | Finite volume gives zero without a source. |
| $O(N)$ model | vector $\phi^i$ | $O(N)\to O(N-1)$ symmetry breaking. | Low dimensions and finite temperature require Mermin–Wagner care. |
| Antiferromagnet | staggered magnetization | Néel ordering. | The order parameter may include microscopic lattice momentum. |
| Chiral QCD | $\langle\bar q q\rangle$ or chiral matrix condensate | Chiral symmetry realization. | Composite-operator renormalization and quark masses matter. |
| Superfluid | complex condensate or phase stiffness | Breaking of particle-number symmetry in an effective description. | In gauge-coupled systems, gauge-invariant diagnostics are required. |
| Scalar Higgs model | gauge-invariant composites, spectrum, line response | Higgs-like behavior. | The elementary scalar VEV is gauge dependent. |

The table is deliberately mixed: high-energy, statistical, and condensed-matter examples share the same diagnostic grammar. The physical interpretation depends on the symmetry, dimension, and observable algebra.

## Gauge invariance and Elitzur's warning

Gauge redundancy is not a physical symmetry that can be spontaneously broken in the same way as a global symmetry. Therefore a gauge-variant local field cannot serve as a physical order parameter.

In a gauge theory with scalar field $\Phi$, a gauge choice may produce

$$
\langle\Phi\rangle_{\text{gauge fixed}}\neq0.
$$

This can be a useful computational shorthand, especially in weakly coupled Higgs regimes. But physical statements must be phrased using gauge-invariant data, such as:

- masses and scattering of gauge-invariant excitations;
- expectation values or laws for Wilson and ’t Hooft loops;
- response to background fields for genuine global symmetries;
- boundary conditions and superselection sectors;
- gauge-invariant composite operators such as $\Phi^\dagger\Phi$.

This is not pedantry. It prevents a common false inference: “the gauge symmetry is broken, therefore the phase is physically distinct.” Gauge-Higgs systems can have regions that look very different perturbatively but are analytically connected when no exact global or generalized symmetry distinguishes them.

Global symmetries are different. If $\mathcal O$ is gauge invariant but transforms under a physical global symmetry, then its VEV can diagnose spontaneous breaking of that global symmetry.

## Renormalization of composite operators

Local order parameters in QFT are usually composite operators. Composite operators require renormalization.

A bare operator $\mathcal O_0$ is related to renormalized operators by mixing:

$$
\mathcal O_{0,a}=Z_a{}^b(\mu)\mathcal O_b(\mu)+\text{possible lower-dimensional mixings}.
$$

The expectation value $\langle\mathcal O(\mu)\rangle$ can therefore depend on the renormalization scale and scheme. In some cases there is additive mixing with the identity operator. Then the absolute value of the condensate is not universal, even though symmetry realization and scaling behavior can be meaningful.

For example, a chiral condensate such as $\langle\bar q q\rangle$ is a central diagnostic of chiral symmetry breaking, but its numerical value depends on the renormalization convention. The physical claims are about the symmetry pattern, Ward identities, low-energy modes, and response to quark masses, not about a scheme-free standalone number.

A reliable local-order-parameter statement should therefore say:

| Question | Good practice |
|---|---|
| Is the operator renormalized? | Specify the scheme or focus on invariant statements. |
| Can it mix with the identity? | Subtract or compare phases carefully. |
| Is it gauge invariant? | If not, treat it as gauge-fixed auxiliary language. |
| Is it tied to a global symmetry? | State the transformation and unbroken subgroup. |
| Is the limit finite-volume or infinite-volume? | State the source and thermodynamic order of limits. |

## Local order without a nonzero one-point function

A phase can have local order even when the simplest one-point function vanishes.

Examples include:

- **antiferromagnets**, where the order parameter carries a lattice momentum and appears as staggered magnetization rather than net magnetization;
- **nematic order**, where the order parameter is quadratic in a vector and invariant under $\mathbf n\sim-\mathbf n$;
- **explicitly broken systems**, where no exact order parameter vanishes but scaling and response still reveal a nearby transition;
- **finite-volume simulations**, where the one-point function vanishes but the two-point function develops a plateau;
- **critical points**, where the order parameter may vanish at the transition but its correlator has power-law decay.

The moral is that local diagnostics include more than $\langle\mathcal O\rangle$. They include correlation functions, finite-size scaling, susceptibilities, Binder ratios, operator spectra, and response to sources. The VEV is the headline, not the whole article.

## Diagnostic workflow

Given a proposed local order parameter, check it in this order.

| Step | Question | Failure mode |
|---:|---|---|
| 1 | What symmetry or phase property is being tested? | The operator is nonzero but does not diagnose the claimed phase. |
| 2 | Is the operator local and gauge invariant? | The “order parameter” is a gauge artifact. |
| 3 | Does the operator transform nontrivially under a physical symmetry? | The VEV may be a condensate but not a symmetry-breaking order parameter. |
| 4 | What source selects the phase? | The finite-volume answer averages over vacua. |
| 5 | What is the order of limits? | The thermodynamic phase is lost. |
| 6 | What is the long-distance correlator? | A one-point function alone is misleading. |
| 7 | How is the operator renormalized? | A numerical condensate is scheme-dependent. |
| 8 | What other diagnostics agree? | A local order parameter is incomplete for gauge or topological phases. |

In nonperturbative QFT, the last row is not optional. A local VEV should be compared with spectra, line operators, finite-volume dependence, and response functions when the phase claim is subtle.

## Common pitfalls

**Taking finite volume too literally.** A finite system with an exact symmetry usually has a symmetric ground state. Spontaneous symmetry breaking appears after an infrared limit, often with a source.

**Using a gauge-variant field as a physical order parameter.** A gauge-fixed scalar VEV is useful shorthand, not a gauge-invariant diagnostic by itself.

**Confusing a condensate with an order parameter.** A condensate is any nonzero expectation value. It becomes an order parameter only when its value distinguishes a symmetry realization or phase in a controlled way.

**Forgetting composite-operator renormalization.** Local products such as $\bar q q$, $\phi^2$, or $F_{\mu\nu}F^{\mu\nu}$ need renormalization and can mix with other operators.

**Assuming zero means unbroken.** A zero VEV can come from finite volume, wrong source limit, wrong operator quantum numbers, averaging over vacua, gauge redundancy, or spacetime symmetry constraints.

**Assuming nonzero means broken.** A nonzero scalar such as $\langle\phi^2\rangle$ may be present in both phases and may not transform under the symmetry being tested.

**Forgetting dimension.** Continuous symmetry breaking behaves differently in low dimensions, especially at finite temperature or in two-dimensional Euclidean statistical systems.

**Overusing mean-field pictures.** Landau potentials are excellent maps of ideas, but fluctuations and RG can change the terrain.

## Relations to other pages

This page gives the local part of the diagnostic toolkit. [Disorder Parameters](/nonperturbative-qft/order-parameters-diagnostics/disorder-parameters/) explains complementary diagnostics built from twists, defects, and dual variables. [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/) explains what VEVs mean as state-dependent quantities, while [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/) explains the vacuum-selection mechanism.

The next diagnostic layers are correlation lengths, mass gaps, spectral densities, and line operators. Those pages will connect local order parameters to measurable long-distance decay, transfer-matrix spectra, confinement diagnostics, and thermal phase structure.

For gauge theories, this page should be read with extra suspicion. Wilson loops, ’t Hooft loops, Polyakov loops, and higher-form symmetry language often carry information no local gauge-invariant scalar can see.

## Research status

**Established.** Local order parameters, source limits, cluster decomposition in pure phases, susceptibilities, and Landau-type diagnostics are standard tools in statistical field theory, condensed matter, and relativistic QFT. Their use in ordinary global symmetry breaking is conceptually mature.

**Convention-dependent.** The numerical value of a composite-operator condensate can depend on normalization, scheme, subtraction, and scale. The symmetry pattern and scaling behavior are usually more physical than the bare number.

**Subtle.** Gauge theories require gauge-invariant diagnostics. Gauge-fixed VEVs can guide perturbation theory but do not by themselves define physical phases.

**Active.** In strongly coupled gauge theories, finite-density systems, topological phases, and systems with generalized symmetries, deciding which set of diagnostics is complete remains a live research problem.

## Exercises

### Exercise 1: Order of limits in a broken phase

Suppose a finite-volume theory has an exact $\mathbb Z_2$ symmetry and an odd operator $\phi$. Explain why $\langle\phi\rangle_{L,0}=0$ at finite $L$, even if the infinite-volume theory has two broken vacua. Then write the source-limit definition of the positive magnetization.

<details>
<summary><strong>Solution</strong></summary>

At finite volume the Hamiltonian or Euclidean path integral respects the exact $\mathbb Z_2$ symmetry. If the state or ensemble is also symmetry invariant, then

$$
\langle\phi\rangle_{L,0}=\langle g^{-1}\phi g\rangle_{L,0}=-\langle\phi\rangle_{L,0},
$$

so $\langle\phi\rangle_{L,0}=0$.

The positive broken-phase magnetization is defined by adding a small source $h\phi$, taking the thermodynamic limit, and then removing the source:

$$
v_+=\lim_{h\to0^+}\lim_{L\to\infty}\langle\phi\rangle_{L,h}.
$$

The limit $h\to0^+$ selects the positive pure phase. The negative phase is obtained with $h\to0^-$.

</details>

### Exercise 2: Mean-field order parameter

For

$$
V(\phi)=\frac{r}{2}\phi^2+\frac{u}{4}\phi^4-h\phi,
\qquad u>0,
$$

find the $h=0$ minima for $r>0$ and $r<0$. What is the mean-field order parameter in the broken phase?

<details>
<summary><strong>Solution</strong></summary>

At $h=0$, stationary points satisfy

$$
V'(\phi)=r\phi+u\phi^3=\phi(r+u\phi^2)=0.
$$

For $r>0$, the only real minimum is $\phi=0$ because

$$
V''(0)=r>0.
$$

For $r<0$, $\phi=0$ is a maximum and the two minima are

$$
\phi_\pm=\pm\sqrt{\frac{-r}{u}}.
$$

Thus the source-selected mean-field order parameters are

$$
v_\pm=\pm\sqrt{\frac{-r}{u}}.
$$

</details>

### Exercise 3: Long-range order from a two-point function

Assume a pure translation-invariant phase satisfies cluster decomposition. Show that if $\langle\mathcal O\rangle=v$, then

$$
\lim_{|x|\to\infty}\langle\mathcal O(x)\mathcal O(0)\rangle=v^2
$$

for a real scalar operator. What is the connected correlator in this limit?

<details>
<summary><strong>Solution</strong></summary>

Cluster decomposition says that widely separated local operators factorize in a pure phase:

$$
\lim_{|x|\to\infty}\langle\mathcal O(x)\mathcal O(0)\rangle
=\langle\mathcal O(x)\rangle\langle\mathcal O(0)\rangle.
$$

Translation invariance gives $\langle\mathcal O(x)\rangle=\langle\mathcal O(0)\rangle=v$, so the limit is $v^2$.

The connected correlator is

$$
C(x)=\langle\mathcal O(x)\mathcal O(0)\rangle-\langle\mathcal O\rangle^2.
$$

Therefore

$$
\lim_{|x|\to\infty}C(x)=0.
$$

The full correlator has a nonzero plateau, while the connected correlator decays.

</details>

### Exercise 4: Gauge-variant VEVs

A gauge-fixed calculation in an Abelian Higgs model gives $\langle\Phi\rangle\neq0$. Explain why this is not by itself a gauge-invariant order parameter. Name two gauge-invariant diagnostics that can be used instead.

<details>
<summary><strong>Solution</strong></summary>

$\Phi$ transforms under the local gauge redundancy, so its one-point function depends on gauge choice. A gauge redundancy is not a physical global symmetry, and a gauge-variant VEV cannot by itself distinguish physical phases.

Gauge-invariant alternatives include:

$$
\langle\Phi^\dagger\Phi\rangle,
$$

although this scalar may not sharply distinguish phases by itself; masses and correlation functions of gauge-invariant composite operators; Wilson-loop and ’t Hooft-loop behavior; response to external probes; and the spectrum of gauge-invariant excitations.

The useful perturbative statement “the scalar has a VEV” should be translated into such gauge-invariant language when making physical claims.

</details>

## References

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for order parameters, source limits, cluster properties, critical scaling, and statistical-field-theory conventions.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on spontaneous symmetry breaking, effective potentials, and functional methods.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for symmetry realization, cluster decomposition, and QFT foundations.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for spontaneous symmetry breaking, gauge-theory cautions, and spectral diagnostics.
- C. P. Burgess, *Introduction to Effective Field Theory*, for order parameters in EFT, chiral symmetry breaking, and symmetry-realization language.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for order parameters, gauge theories, topological phases, and condensed-matter examples.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for broken symmetry, response functions, and RG diagnostics.

## Version history

- **2026-06-26:** Initial polished draft.
