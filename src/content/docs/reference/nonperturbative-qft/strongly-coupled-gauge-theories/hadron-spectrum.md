---
title: "Hadron Spectrum"
description: "Explains how QCD's nonperturbative color-singlet spectrum is defined and extracted from gauge-invariant correlators, finite-volume levels, and spectral functions."
sidebar:
  label: "Hadron Spectrum"
  order: 3
level: Advanced
status: "Polished draft"
source: "Srednicki; Schwartz; Shifman; Weinberg, Vol. II; lattice QCD reviews."
topics:
  - hadron spectrum
  - QCD
  - mesons
  - baryons
  - resonances
  - lattice QCD
  - spectral decomposition
  - finite volume
  - scattering
  - large N
canonicalTopics:
  - nonperturbative-qft
  - strongly-coupled-gauge-theories
  - hadron-spectrum
  - qcd
  - spectral-density
  - lattice-qcd
researchStatus:
  established:
    - "The low-energy QCD spectrum is organized by gauge-invariant color-singlet states and can be extracted nonperturbatively from Euclidean correlation functions, especially on the lattice."
  active:
    - "Excited spectra, resonance parameters, multi-hadron channels, exotic candidates, real-time spectral functions, and finite-density spectra remain active computational and conceptual frontiers."
---

## Summary

The hadron spectrum is the set of color-singlet states, thresholds, and resonances created by gauge-invariant operators in QCD. It is nonperturbative because the physical low-energy particles are not the quark and gluon fields in the microscopic Lagrangian. They are bound states and collective states of the strongly coupled theory.

A Euclidean two-point function of a zero-momentum gauge-invariant operator has the spectral form

$$
C(t)=\langle \mathcal O(t)\mathcal O^\dagger(0)\rangle
=\sum_n |Z_n|^2e^{-E_nt},
\qquad
Z_n=\langle0|\mathcal O|n\rangle,
$$

on a finite spatial volume. At large Euclidean time, the lowest state with the same quantum numbers dominates. With a matrix of operators, one can extract several finite-volume levels in a channel. These levels are the raw nonperturbative data from which masses, thresholds, and scattering information are inferred.

The spectrum is not just a list of “quark contents.” Quark model labels are useful spectroscopy language, but QCD defines hadrons through gauge-invariant states, correlation functions, symmetries, and scattering amplitudes. The same channel can contain quark–antiquark operators, gluonic operators, molecular-looking two-hadron operators, tetraquark-like operators, and finite-volume mixtures of all of them.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Pipeline diagram showing gauge-invariant operators forming a Euclidean correlator matrix, yielding finite-volume energy levels and then infinite-volume masses, thresholds, and resonance poles.](/figures/nonperturbative-qft/hadron-spectrum-correlator-map.svg)

<figcaption>

Hadron spectroscopy is an inverse problem. Gauge-invariant operators define a correlator matrix; its Euclidean-time falloff gives finite-volume energy levels; those levels are interpreted as stable masses, thresholds, or scattering data depending on the channel.

</figcaption>
</figure>

## Prerequisites

You should know [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/), [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/), [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/), [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), and [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/).

## Core idea

A hadron is a state in the QCD Hilbert space, not a fundamental field in the QCD Lagrangian. The reliable definition is operational:

1. choose gauge-invariant operators with definite quantum numbers;
2. compute their correlation functions;
3. decompose those correlators into energy eigenstates or spectral densities;
4. interpret the resulting poles, cuts, finite-volume levels, and thresholds.

The microscopic quark and gluon fields are still essential. They build the operators, determine the symmetries, and govern short-distance processes. But the asymptotic low-energy particles are color singlets.

## Setup and conventions

We work in QCD-like gauge theories on a finite spatial volume when discussing Euclidean energy extraction. The Euclidean time coordinate is written $t$ in this page, and we assume $t>0$. A zero-momentum operator is obtained by spatially summing a local or extended gauge-invariant operator,

$$
\mathcal O_i(t)=\int d^3\mathbf x\,\mathcal O_i(t,\mathbf x),
$$

or by the corresponding lattice sum in a lattice regularization.

The correlator matrix is

$$
C_{ij}(t)=\langle \mathcal O_i(t)\mathcal O_j^\dagger(0)\rangle .
$$

With a finite-volume Hamiltonian and a discrete spectrum,

$$
C_{ij}(t)=\sum_n Z_i^{(n)}Z_j^{(n)*}e^{-E_nt},
\qquad
Z_i^{(n)}=\langle0|\mathcal O_i|n\rangle .
$$

This formula is the backbone of Euclidean hadron spectroscopy.

## Gauge-invariant interpolating operators

The word “interpolating” is important. An operator can create a state from the vacuum if it has the right quantum numbers and nonzero overlap. It does not have to look exactly like the dominant physical wavefunction.

Typical schematic operators are:

| Channel | Schematic operator | Comments |
|---|---|---|
| Meson | $\bar q\Gamma q$ | Creates color-singlet quark–antiquark channels. |
| Baryon in $SU(3)$ | $\epsilon_{abc}q^aq^bq^c$ | Creates baryon-number-one channels. |
| Glueball | $\operatorname{tr}F_{\mu\nu}F^{\mu\nu}$, $\operatorname{tr}F_{\mu\nu}\widetilde F^{\mu\nu}$ | Pure-gauge quantum numbers; also mix with mesonic operators when quarks are dynamical. |
| Two-hadron | $\mathcal O_A\mathcal O_B$ | Essential for thresholds, scattering, and resonances. |
| Hybrid or exotic | $\bar q\Gamma F_{\mu\nu}q$, extended Wilson-line operators | Useful for channels not well described by the simplest quark model. |

The same physical finite-volume state may have overlap with many operators. Therefore a good spectrum calculation uses an operator basis, not a single favorite operator.

:::note[Operators are probes, not identities]
Calling an operator “tetraquark-like” or “molecular-like” describes the probe used in a calculation, not automatically the ontology of the state. QCD states are identified by their quantum numbers, pole structure, finite-volume behavior, and overlaps with many probes.
:::

## Spectral decomposition and effective masses

For a single operator with nonzero overlap with the lightest state in its channel,

$$
C(t)=|Z_0|^2e^{-E_0t}+|Z_1|^2e^{-E_1t}+\cdots .
$$

The effective mass

$$
m_{\mathrm{eff}}(t)=\log\frac{C(t)}{C(t+a_t)}
$$

approaches $E_0a_t$ on a lattice with Euclidean time spacing $a_t$, or $E_0$ in the continuum version with a derivative definition. The approach is controlled by excited-state gaps:

$$
m_{\mathrm{eff}}(t)=E_0+O(e^{-(E_1-E_0)t}).
$$

In practice, the large-$t$ region is also where statistical noise usually grows. Spectroscopy is therefore a compromise between suppressing excited states and preserving enough signal to fit.

## Correlator matrices and the variational idea

To extract multiple states, use a basis $\mathcal O_i$ and the matrix $C_{ij}(t)$. A standard variational strategy solves a generalized eigenvalue problem,

$$
C(t)v_n(t,t_0)=\lambda_n(t,t_0)C(t_0)v_n(t,t_0),
$$

with asymptotic behavior

$$
\lambda_n(t,t_0)\sim e^{-E_n(t-t_0)}
$$

up to excited-state contamination. The eigenvectors identify combinations of operators with enhanced overlap onto particular finite-volume states.

This is why operator design matters. A basis containing only single-hadron-looking operators may miss or distort two-hadron levels. A basis containing only local bilinears may have poor overlap onto extended states. A basis that respects the relevant lattice symmetry but not the continuum target carefully enough can mix channels in confusing ways.

## Quantum numbers and channels

In infinite-volume continuum QCD, states are classified by spin, parity, charge conjugation when applicable, flavor, baryon number, strangeness, isospin, and other global quantum numbers. For mesons one often writes $J^{PC}$, while baryons are classified by $J^P$ and flavor quantum numbers.

On a cubic lattice, rotational symmetry is reduced from $SO(3)$ to the cubic group. A lattice channel therefore contains pieces of several continuum spins. Recovering continuum spin assignments requires comparing multiple irreducible representations and taking the continuum limit.

The most important practical distinction is between:

| Type of channel | Infinite-volume meaning | Finite-volume signal |
|---|---|---|
| Stable single particle | Pole below all strong-decay thresholds | Isolated level with exponential correlator falloff. |
| Two-particle threshold | Start of a continuum cut | Discrete tower of two-particle finite-volume levels. |
| Resonance | Pole on an unphysical sheet of the scattering amplitude | Avoided level motion and phase-shift behavior, not simply one exponential. |
| Bound state near threshold | Pole below threshold | Level below threshold with volume dependence distinct from scattering states. |

The punchline is that finite-volume levels are not automatically resonance masses. They are inputs to a scattering analysis.

## Resonances and finite volume

Most excited hadrons are resonances. In infinite-volume scattering theory, a resonance is associated with a pole of the analytically continued scattering amplitude. It is not, in general, a normalizable stationary state with a real energy and an exponential Euclidean correlator $e^{-Mt}$.

In a finite box, however, the spectrum is discrete and real. Multi-hadron scattering states appear as a tower of levels. The interaction shifts those levels relative to noninteracting energies. In favorable elastic two-body regimes, finite-volume energies determine infinite-volume phase shifts through Lüscher-type relations. Resonance masses and widths are then inferred from the energy dependence of the phase shift or amplitude.

This distinction is one of the main conceptual repairs needed in hadron spectroscopy. A bump in an experimental distribution, a level in a finite box, a quark-model basis vector, and a pole of the $S$-matrix are related but not identical objects.

## Chiral physics inside the spectrum

Chiral symmetry breaking is visible in the spectrum in two complementary ways.

First, the pseudoscalar mesons are much lighter than typical hadrons because they are pseudo-Goldstone bosons. Their masses vanish in the chiral limit according to relations such as

$$
m_\pi^2\propto m_u+m_d.
$$

Second, most other hadron masses remain of order $\Lambda_{\mathrm{QCD}}$ in the chiral limit. The proton mass, for example, is not mostly generated by the explicit up and down quark masses. It is a nonperturbative mass scale of the strongly interacting theory.

Chiral dynamics also controls multi-pion thresholds, finite-volume effects, and low-energy scattering. Therefore even a spectrum calculation that is not “about pions” often needs chiral reasoning to interpret its light-quark-mass dependence.

## Partons, quark models, and spectra

The parton model describes high-energy scattering using quarks and gluons as short-distance degrees of freedom. Hadron spectroscopy describes color-singlet states at long distance. These are compatible descriptions of the same QFT.

The quark model remains a useful approximate language for organizing many hadrons. It gives labels such as $q\bar q$, $qqq$, radial excitation, orbital excitation, hybrid, and multiquark candidate. But in QCD those labels are not exact superselection sectors. States with the same conserved quantum numbers can mix.

A better hierarchy is:

$$
\text{symmetry channel}
\quad\Rightarrow\quad
\text{correlator and scattering data}
\quad\Rightarrow\quad
\text{interpretive labels}.
$$

Do not reverse the arrows. The quark-model label is an interpretation of the QCD data, not the definition of the state.

## Large-N intuition

In the ’t Hooft large-$N$ limit with fixed $N_f$, confinement plus large-$N$ counting suggests a simplified hadronic world. Mesons and glueballs become narrow, and connected scattering amplitudes are suppressed by powers of $1/N$. Schematically,

$$
\Gamma_{\mathrm{meson}}=O(1/N),
\qquad
\Gamma_{\mathrm{glueball}}=O(1/N^2).
$$

This gives a reason why a resonance-dominated description of hadron physics is often useful. At $N=3$, widths are not zero, and channels can be messy, but the large-$N$ limit offers a controlled organizing principle.

Large-$N$ reasoning does not compute the real spectrum from first principles by itself. It explains patterns: narrow resonances, suppressed mixing in some sectors, planar organization, and the plausibility of string-like descriptions of confining flux tubes.

## What a spectrum calculation must control

A careful nonperturbative spectrum calculation has several layers of checks:

| Check | Why it matters |
|---|---|
| Operator basis | Determines overlap with single-hadron, multi-hadron, and exotic-looking states. |
| Finite volume | Distinguishes bound states, scattering states, thresholds, and resonances. |
| Continuum limit | Removes discretization artifacts and restores rotational symmetry. |
| Quark-mass dependence | Connects simulated masses to the chiral and physical regimes. |
| Scale setting | Converts dimensionless energies into physical units. |
| Symmetry assignment | Prevents mixing of unrelated channels and identifies continuum quantum numbers. |
| Excited-state contamination | Avoids mistaking fit artifacts for physical levels. |

The theme is the same as everywhere in nonperturbative QFT: the observable is defined cleanly, but extracting it requires controlling limits.

## Common pitfalls

**Identifying interpolating operators with particles.** An operator creates whatever states share its quantum numbers and have nonzero overlap. The state is not identical to the operator’s schematic quark content.

**Reading finite-volume levels as resonance masses.** A resonance is an infinite-volume scattering-pole concept. Finite-volume levels must be converted into scattering information before one quotes resonance parameters.

**Ignoring multi-hadron operators.** Excited spectra often contain levels dominated by two- or three-hadron physics. Leaving such operators out can produce misleading plateaus or missing states.

**Thinking quarks are useless because hadrons are color singlets.** Quark and gluon fields are indispensable microscopic variables and short-distance degrees of freedom. They are just not isolated asymptotic states in the confining regime.

**Assuming every hadron has a clean quark-model label.** Mixing is allowed whenever symmetries allow it. Labels such as “tetraquark,” “molecule,” or “hybrid” are useful only when backed by operator overlaps, pole behavior, decay patterns, and controlled approximations.

## Relations to other pages

- [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/) explains why quarks and gluons reorganize into color-singlet states in the infrared.
- [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/) explains why the light pseudoscalar mesons are pseudo-Goldstone bosons rather than ordinary hadrons of order $\Lambda_{\mathrm{QCD}}$.
- [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/) gives the general spectral-representation language behind poles, continua, and positive spectral weights.
- [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) explains how exponential decay of Euclidean correlators diagnoses a gap.
- [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains why finite-volume limits are part of the definition, not a mere computational nuisance.
- [Glueballs](/nonperturbative-qft/strongly-coupled-gauge-theories/glueballs/) specializes the spectral method to pure-gauge operators and the Yang–Mills mass gap.
- [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/) explains the long-distance flux-tube picture behind string-like spectroscopy.
- [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) explains why narrow mesons, glueballs, and string-like intuition become cleaner as $N\to\infty$.

## Research status

The basic definition of the hadron spectrum through gauge-invariant correlators is textbook-standard. Ground-state masses and many low-lying quantities are now routinely accessible in lattice QCD, with controlled continuum and finite-volume analysis in favorable cases.

The frontier is not the existence of hadrons. It is precision and interpretation in difficult regimes: resonances, coupled channels, excited states, exotic candidates, baryon-rich matter, real-time spectral functions, transport, and finite density. The conceptual line remains the same: use gauge-invariant observables, control limits, and distinguish finite-volume levels from infinite-volume scattering data.

## Exercises

### Exercise 1: Derive the spectral decomposition

Let $\mathcal O(t)=e^{Ht}\mathcal O(0)e^{-Ht}$ in Euclidean time and insert a complete set of finite-volume energy eigenstates. Show that

$$
C(t)=\langle0|\mathcal O(t)\mathcal O^\dagger(0)|0\rangle
=\sum_n |\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)t}.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert the identity $1=\sum_n |n\rangle\langle n|$ between the two operators:

$$
C(t)=\sum_n\langle0|e^{Ht}\mathcal O(0)e^{-Ht}|n\rangle
\langle n|\mathcal O^\dagger(0)|0\rangle .
$$

Using $H|n\rangle=E_n|n\rangle$ and $\langle0|e^{Ht}=e^{E_0t}\langle0|$ gives

$$
C(t)=\sum_n e^{-(E_n-E_0)t}
\langle0|\mathcal O(0)|n\rangle
\langle n|\mathcal O^\dagger(0)|0\rangle.
$$

If $\mathcal O^\dagger$ is the Hermitian conjugate probe, the product of matrix elements is $|\langle0|\mathcal O|n\rangle|^2$ up to the chosen convention for which operator creates the state.

</details>

### Exercise 2: Effective-mass contamination

Suppose

$$
C(t)=A_0e^{-E_0t}+A_1e^{-E_1t},
\qquad
E_1>E_0.
$$

Show that the correction to the effective mass is exponentially suppressed by $e^{-(E_1-E_0)t}$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
C(t)=A_0e^{-E_0t}\left[1+r e^{-\Delta E t}\right],
\qquad
r=\frac{A_1}{A_0},
\qquad
\Delta E=E_1-E_0.
$$

For a continuum effective mass $m_{\mathrm{eff}}(t)=-\frac{d}{dt}\log C(t)$,

$$
m_{\mathrm{eff}}(t)=E_0+\frac{r\Delta E e^{-\Delta Et}}{1+r e^{-\Delta Et}}.
$$

At large $t$ this becomes

$$
m_{\mathrm{eff}}(t)=E_0+r\Delta E e^{-\Delta Et}+\cdots .
$$

The lattice log-ratio version gives the same exponential suppression, with coefficients depending on the time spacing.

</details>

### Exercise 3: Why a two-particle threshold becomes a tower

For two weakly interacting identical scalar particles of mass $m$ in a periodic box of side $L$, estimate the noninteracting energies of zero-total-momentum two-particle states.

<details>
<summary><strong>Solution</strong></summary>

Periodic boundary conditions quantize momenta as

$$
\mathbf p=\frac{2\pi}{L}\mathbf n,
\qquad
\mathbf n\in\mathbb Z^3.
$$

Zero total momentum means the two particles carry $\mathbf p$ and $-\mathbf p$. The noninteracting energy is

$$
E_{\mathbf n}=2\sqrt{m^2+\left(\frac{2\pi}{L}\right)^2\mathbf n^2}.
$$

Thus the infinite-volume continuum beginning at $2m$ is replaced in finite volume by a discrete tower. Interactions shift these energies, and those shifts encode scattering information.

</details>

### Exercise 4: Large-N widths

Assume a meson decay amplitude scales as $\mathcal A(M\to M_1M_2)\sim N^{-1/2}$. What is the large-$N$ scaling of the decay width?

<details>
<summary><strong>Solution</strong></summary>

At fixed kinematics, the width is proportional to the squared amplitude times phase space:

$$
\Gamma\propto |\mathcal A|^2\times \text{phase space}.
$$

If the phase space is $O(N^0)$ and $\mathcal A\sim N^{-1/2}$, then

$$
\Gamma\sim \frac{1}{N}.
$$

Thus mesons become narrow at large $N$, which is one reason resonance language becomes cleaner in that limit.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, especially the chapters on QCD, chiral symmetry breaking, Wilson loops, lattice theory, and confinement.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on Yang–Mills theory, lattice gauge theory, QCD, partons, factorization, and spectral decomposition.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for QCD, chiral symmetry, current algebra, and strong-interaction applications.

### Deeper references

- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on phases of gauge theories, confinement, large-$N$, and related lower-dimensional models.
- M. Lüscher, “Two-particle states on a torus and their relation to the scattering matrix,” *Nuclear Physics B* **354** (1991), for the finite-volume scattering relation.
- C. Morningstar, J. Bulava, and related lattice spectroscopy reviews, for modern operator-basis and variational methods in hadron spectroscopy.
- R. F. Dashen and A. V. Manohar, and E. Witten's large-$N$ work, for large-$N$ hadron-spectrum systematics.

## Version history

- **2026-06-27:** Added links to the new Glueballs and QCD String Preview pages.
- **2026-06-27:** Initial polished draft, added after Chiral Symmetry Breaking in the Strongly Coupled Gauge Theories chapter.
