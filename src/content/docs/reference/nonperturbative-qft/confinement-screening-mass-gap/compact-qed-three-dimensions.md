---
title: "Compact QED in Three Dimensions"
description: "Explains Polyakov's mechanism in compact three-dimensional QED: monopole instantons generate a dual-photon mass gap and an electric Wilson-loop area law."
sidebar:
  label: "Compact QED in Three Dimensions"
  order: 12
level: Advanced
status: "Polished draft"
source: "Polyakov, ch. 4; Fradkin ch. 9; Shifman ch. 9; Banks–Myerson–Kogut."
topics:
  - compact QED
  - three-dimensional gauge theory
  - monopole instantons
  - dual photon
  - confinement
  - mass gap
  - sine-Gordon theory
  - Coulomb gas
canonicalTopics:
  - nonperturbative-qft
  - confinement
  - compact-qed
  - monopole-instantons
  - mass-gap
researchStatus:
  established:
    - "Pure compact U(1) gauge theory in 2+1 dimensions confines by Polyakov's monopole-instanton mechanism and has a nonzero mass gap at weak coupling."
  active:
    - "Adding matter, Chern–Simons terms, lattice Berry phases, or gapless fermions can change monopole dynamics and lead to deconfined phases or critical points."
---

## Summary

Pure **compact QED in three spacetime dimensions** is the classic solvable mechanism for confinement. The surprising result is that a theory whose weak-coupling local action looks like Maxwell theory does **not** have a massless photon in the infrared. Compactness allows monopole instantons. Their dilute plasma generates a potential for the dual photon, giving it a mass:

$$
S_{\mathrm{dual}}
=\int d^3x\left[
\frac{g_3^2}{32\pi^2}(\partial_\mu\varphi)^2
+2\zeta(1-\cos\varphi)
\right],
$$

so, for small monopole fugacity $\zeta$,

$$
m_\gamma^2\sim \frac{\zeta}{g_3^2}
$$

up to convention-dependent numerical factors. The photon is replaced by a massive scalar excitation in the dual description.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A pipeline from compact link angles to monopole instantons, a Coulomb gas, a sine-Gordon dual photon, and finally a mass gap plus Wilson-loop area law.](/figures/nonperturbative-qft/compact-qed3-monopole-gas.svg)

<figcaption>

Polyakov's mechanism in compact $\mathrm{QED}_3$: compactness permits monopole instantons; the dilute monopole gas is equivalent to a sine-Gordon theory for the dual photon; the dual photon becomes massive; a Wilson loop forces a dual-photon kink sheet whose tension gives an area law.

</figcaption>
</figure>

The same monopoles also confine electric test charges. A Wilson loop imposes a branch sheet for the dual photon. Because the dual photon is pinned by the cosine potential, that sheet becomes a domain wall with nonzero tension. Therefore

$$
\langle W(C)\rangle\sim e^{-\sigma A(C)}.
$$

This example is precious because it is not merely “strong coupling makes confinement plausible.” It is a controlled weak-coupling semiclassical calculation in which the confining scale is exponentially small but nonzero.

## Prerequisites

Read [Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/) first for the lattice area-law calculation, and [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) for the static-potential interpretation.

You should also know [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), [Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/), [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/), and [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/).

## Core idea

Noncompact Maxwell theory in three spacetime dimensions has a massless photon. Equivalently, it can be dualized to a compact scalar $\varphi$ with a shift symmetry:

$$
F_{\mu\nu}
\sim \frac{g_3^2}{2\pi}\epsilon_{\mu\nu\rho}\partial^\rho\varphi,
\qquad
\varphi\sim\varphi+2\pi.
$$

The shift symmetry forbids a potential for $\varphi$, so the dual photon is massless.

Compact QED is different. The gauge field is an angular variable on the lattice, and field strengths are defined modulo $2\pi$. Compactness allows configurations in which magnetic flux is not conserved smoothly at isolated Euclidean events:

$$
dF=2\pi q\,\delta^{(3)}(x-x_0),
\qquad q\in\mathbb Z.
$$

These events are monopole instantons. They violate the dual-photon shift symmetry down to the discrete periodicity and generate the operator

$$
\zeta e^{i\varphi}+\zeta e^{-i\varphi}=2\zeta\cos\varphi.
$$

Once $\cos\varphi$ appears, the dual photon is massive. A massless Coulomb phase is replaced by a confining phase.

## Setup and conventions

We consider pure compact $U(1)$ gauge theory in $2+1$ Lorentzian dimensions, or equivalently in three-dimensional Euclidean spacetime. The continuum Maxwell action is written schematically as

$$
S_{\mathrm{Maxwell}}
=\frac{1}{4g_3^2}\int d^3x\,F_{\mu\nu}F_{\mu\nu},
$$

where $g_3^2$ has mass dimension one. On a lattice, compactness means the link variable is

$$
U_\ell=e^{iA_\ell},
\qquad
A_\ell\sim A_\ell+2\pi.
$$

A convenient Villain form of the lattice action is

$$
S_{\mathrm{V}}
=\frac{1}{2e_0^2}\sum_p\left((dA)_p-2\pi n_p\right)^2,
\qquad n_p\in\mathbb Z.
$$

The integers $n_p$ are not decorative. They enforce the $2\pi$ periodicity of the gauge field while keeping a Gaussian-looking action. The monopole charge in an elementary cube $c$ is the lattice divergence of these integers:

$$
q_c=\sum_{p\in\partial c} n_p\in\mathbb Z.
$$

In the continuum language, $q_c\neq0$ means the Bianchi identity is violated at a point. That point is a monopole instanton.

## Compact versus noncompact

The word **compact** does a lot of work here. In noncompact QED, the gauge field takes values in the Lie algebra $\mathbb R$. Magnetic flux is conserved by the Bianchi identity

$$
dF=0,
$$

except where one explicitly inserts singular external monopoles. In the pure theory, there are no dynamical monopole instantons.

In compact QED, the microscopic variable is $e^{iA}$, not $A$ itself. Field strength is periodic. Dirac strings whose flux is an integer multiple of $2\pi$ are invisible to Wilson lines of integer electric charge. As a result, configurations with pointlike endpoints of Dirac strings are allowed in the path integral. Those endpoints are monopole instantons.

The practical distinction is:

| Theory | Euclidean monopole instantons? | Infrared result in pure three-dimensional theory |
|---|---:|---|
| noncompact Maxwell | no | massless photon, Coulomb behavior |
| compact QED | yes | monopole plasma, mass gap, confinement |

So the Polyakov mechanism is not a small correction to ordinary perturbation theory. It uses field configurations excluded from the noncompact Gaussian expansion.

## Monopole gas

At weak coupling, an isolated monopole instanton has a large action. Its fugacity is exponentially small,

$$
\zeta\sim e^{-S_0},
$$

up to a determinant prefactor and cutoff-dependent normalization. A dilute gas approximation is then appropriate. The monopole contribution has the schematic Coulomb-gas form

$$
Z_{\mathrm{mon}}
=\sum_{N=0}^{\infty}\frac{\zeta^N}{N!}
\sum_{q_i=\pm1}\int\prod_{i=1}^N d^3x_i\,
\exp\left[-\frac{2\pi^2}{g_3^2}
\sum_{i<j}q_iq_jG(x_i-x_j)
\right],
$$

where $G(x)$ is the three-dimensional Coulomb Green function,

$$
-\nabla^2G(x)=\delta^{(3)}(x),
\qquad
G(x)=\frac{1}{4\pi |x|}.
$$

On a compact spacetime, total magnetic charge must vanish:

$$
\sum_i q_i=0.
$$

The essential physics is screening. A three-dimensional Coulomb gas of monopoles and antimonopoles screens magnetic fields. In the dual language, screening becomes a mass for the dual photon.

Higher-charge monopoles with $|q|>1$ are allowed, but at weak coupling they are more strongly suppressed and tend to be represented by multiple unit monopoles. The leading dilute gas keeps $q=\pm1$.

## Dual sine-Gordon theory

The Coulomb gas has a standard field representation. Introduce a compact scalar $\varphi$ and use the Gaussian identity that rewrites Coulomb interactions as exchange of $\varphi$. Summing over $q=\pm1$ monopoles generates exponentials $e^{\pm i\varphi}$, and hence a cosine.

The result is the dual sine-Gordon action

$$
S_{\mathrm{dual}}
=\int d^3x\left[
\frac{g_3^2}{32\pi^2}(\partial_\mu\varphi)^2
+2\zeta(1-\cos\varphi)
\right].
$$

The additive constant is chosen so that the minimum has zero potential energy. Expanding near $\varphi=0$ gives

$$
2\zeta(1-\cos\varphi)
=\zeta\varphi^2+O(\varphi^4).
$$

With the displayed kinetic normalization, the dual-photon mass is

$$
m_\gamma^2
=\frac{32\pi^2\zeta}{g_3^2}
$$

in this convention. The precise coefficient is less universal than the conclusion:

$$
m_\gamma>0
\quad\text{whenever}\quad
\zeta>0.
$$

Because $\zeta$ is exponentially small at weak coupling, the mass gap is also exponentially small. That is why ordinary perturbation theory misses it entirely.

## Wilson loop as a dual kink sheet

How does the mass gap imply confinement of electric probes? The Wilson loop is the key. Insert a Wilson loop of integer electric charge along a closed curve $C$:

$$
W_q(C)=\exp\left(iq\oint_C A\right).
$$

In the dual description, this insertion forces the dual scalar $\varphi$ to jump by $2\pi q$ across a surface $\Sigma$ with boundary

$$
\partial\Sigma=C.
$$

If the dual photon were massless, the cost of such a discontinuity would be Coulombic. But the monopole-generated cosine potential pins $\varphi$ near its minima

$$
\varphi=2\pi n.
$$

A surface across which $\varphi$ jumps by $2\pi q$ is therefore a sine-Gordon domain wall. Its action is proportional to its area:

$$
S_{\mathrm{wall}}\approx \sigma_q A(\Sigma).
$$

The path integral chooses the least costly surface at large loop size, giving

$$
\langle W_q(C)\rangle
\sim \exp[-\sigma_q A_{\min}(C)].
$$

For a rectangular loop,

$$
V_q(r)\sim \sigma_q r.
$$

This is confinement. The electric flux tube is the dual-photon kink sheet viewed in Hamiltonian language.

## String tension scale

The domain-wall tension can be estimated from the sine-Gordon action. Parametrically,

$$
\sigma\sim g_3\sqrt{\zeta}
\sim g_3^2 m_\gamma,
$$

up to normalization conventions. The important point is that it is nonzero but exponentially small at weak coupling:

$$
\sigma\propto e^{-S_0/2}
$$

in the simplest semiclassical estimate.

This hierarchy is the signature of a genuinely nonperturbative effect. In powers of $g_3^2$, the answer is invisible; it is controlled by monopole fugacity.

The result should not be confused with the strong-coupling plaquette area law. Both produce an area law, but the mechanisms are different:

| Mechanism | Regime | Origin of area law |
|---|---|---|
| lattice strong-coupling expansion | large bare coupling | plaquette surfaces tile the Wilson loop |
| Polyakov compact QED₃ | weak coupling, dilute monopoles | monopole plasma generates dual-photon domain wall |

The two pictures are expected to describe the same confining phase of pure compact QED₃, but the weak-coupling calculation gives a much sharper semiclassical mechanism.

## Why three dimensions are special

A monopole in three Euclidean dimensions is a point event. Point events form a gas, and that gas screens. This is why compact QED in $2+1$ dimensions confines even at weak coupling.

In four Euclidean dimensions, the analogous monopole objects are worldlines, not point events. Pure compact $U(1)$ lattice gauge theory in four dimensions has a strong-coupling confining phase and a weak-coupling Coulomb phase. The weak-coupling phase has a massless photon. The phase transition is possible because monopole loops can be dilute and small rather than proliferating through the vacuum.

The dimension count is therefore:

| Euclidean dimension | Magnetic object in compact $U(1)$ | Weak-coupling behavior |
|---:|---|---|
| $3$ | monopole instanton events | monopole plasma, mass gap, confinement |
| $4$ | monopole worldlines | Coulomb phase can survive at weak coupling |

This is one of the best examples where topology, dimension, and nonperturbative physics are inseparable.

## Matter and caveats

The pure theory is the clean Polyakov model. Adding matter can change the conclusion.

Dynamical electrically charged matter can screen Wilson loops. Then a fundamental Wilson loop need not obey an asymptotic area law, even if the compact gauge dynamics still generate a gap in some sector.

Gapless matter can also change monopole physics. In theories such as QED₃ with many massless fermions, monopole operators acquire scaling dimensions, and their relevance or irrelevance becomes a dynamical question. In condensed-matter applications, Berry phases can attach lattice quantum numbers to monopoles, causing monopole proliferation to break lattice symmetries rather than producing a featureless confined phase.

Chern–Simons terms change the Gauss law and the quantum numbers of monopoles. They can obstruct or alter the simple monopole-gas story.

So the careful statement is:

$$
\text{pure compact }U(1)\text{ gauge theory in }2+1\text{ dimensions confines.}
$$

Do not silently export that statement to every compact gauge theory with matter.

## Common pitfalls

**Forgetting compactness.** Noncompact Maxwell theory in three dimensions has no dynamical monopole instantons in the pure path integral. The mass gap comes from compactness.

**Calling the monopoles particles.** In $2+1$ Lorentzian dimensions, the monopoles in the Euclidean path integral are instanton events. In one higher dimension, related monopoles become particle worldlines.

**Treating the dual photon mass as perturbative.** The mass is proportional to a monopole fugacity. It is exponentially small at weak coupling and invisible to ordinary perturbation theory.

**Confusing the Wilson-loop area law with a local order parameter.** The confinement diagnostic is an extended-operator law. In the pure compact theory it is sharp; with dynamical matter it may be screened.

**Ignoring lattice Berry phases or gapless matter.** In condensed-matter gauge theories, monopole events may carry microscopic quantum numbers. Their proliferation can imply valence-bond order, not just a featureless confined vacuum.

## Relations to other pages

[Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/) gives the lattice large-bare-coupling area-law calculation. This page gives the weak-coupling semiclassical monopole mechanism in a specific Abelian theory.

[Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/) and [Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/) explain the general saddle and gas logic used here.

[Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/) explains magnetic charge as a solitonic or topological object. Compact QED₃ uses the Euclidean instanton version of that magnetic topology.

[’t Hooft Loop and Duality](/nonperturbative-qft/confinement-screening-mass-gap/thooft-loop-and-duality/) gives the magnetic line-operator diagnostic complementary to Wilson loops. In compact QED₃, electric confinement is produced by magnetic monopole disorder. [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/) and [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/) explain the two outputs of the mechanism in a more general language: a gapped physical spectrum and a confining electric tube. [Confinement Mechanisms](/nonperturbative-qft/confinement-screening-mass-gap/confinement-mechanisms/) compares this controlled monopole plasma with other confinement pictures.

## Research status

**Established.** Polyakov's mechanism is a standard controlled result for pure compact $U(1)$ gauge theory in $2+1$ dimensions. The monopole gas generates a dual-photon mass and an electric Wilson-loop area law.

**Established but model-dependent.** The sine-Gordon dual description is most transparent in the weak-coupling dilute-gas regime and in Villain-like formulations where compactness is explicit. The qualitative conclusion persists through the pure compact theory's confining phase.

**Active.** The fate of monopoles in gauge theories with gapless matter, Chern–Simons terms, supersymmetry, lattice Berry phases, or global-symmetry constraints remains a major tool in modern studies of deconfined criticality, spin liquids, and three-dimensional conformal gauge theories.

## Exercises

### Exercise 1: Dual-photon mass

Start from

$$
S=\int d^3x\left[
\frac{g_3^2}{32\pi^2}(\partial\varphi)^2
+2\zeta(1-\cos\varphi)
\right].
$$

Expand near $\varphi=0$ and extract the mass of the canonically normalized scalar.

<details><summary><strong>Solution</strong></summary>

Use

$$
1-\cos\varphi=\frac12\varphi^2+O(\varphi^4).
$$

Then the quadratic action is

$$
S_2=\int d^3x\left[
\frac{g_3^2}{32\pi^2}(\partial\varphi)^2
+\zeta\varphi^2
\right].
$$

Write the kinetic term as $\frac12 Z(\partial\varphi)^2$, with

$$
Z=\frac{g_3^2}{16\pi^2}.
$$

The mass term is $\frac12 Zm_\gamma^2\varphi^2$, so

$$
\frac12 Zm_\gamma^2=\zeta,
\qquad
m_\gamma^2=\frac{2\zeta}{Z}
=\frac{32\pi^2\zeta}{g_3^2}.
$$

Different normalizations of $\varphi$ shift the numerical coefficient, but not the conclusion $m_\gamma^2\propto \zeta/g_3^2$.

</details>

### Exercise 2: Why noncompact QED₃ is different

Explain why the monopole-generated term $2\zeta\cos\varphi$ is absent in noncompact pure Maxwell theory.

<details><summary><strong>Solution</strong></summary>

In noncompact Maxwell theory, the gauge field is real-valued rather than angle-valued. The Bianchi identity $dF=0$ holds in the pure path integral, so there are no dynamical point events with $dF=2\pi q\delta^{(3)}(x-x_0)$. In the dual scalar language, this gives a continuous shift symmetry $\varphi\to\varphi+\alpha$. The operator $e^{i\varphi}$ is not generated because it would violate that shift symmetry. Therefore the cosine potential is absent and the dual photon remains massless.

</details>

### Exercise 3: Domain wall implies area law

Assume a Wilson loop forces the dual scalar to jump by $2\pi$ across a surface $\Sigma$ with boundary $C$, and that the sine-Gordon kink has tension $\sigma$. Show that the large-loop behavior is an area law.

<details><summary><strong>Solution</strong></summary>

A field configuration satisfying the Wilson-loop boundary condition must contain a kink sheet ending on $C$. If the sheet has tension $\sigma$, its Euclidean action is approximately

$$
S_{\mathrm{sheet}}=\sigma A(\Sigma).
$$

At large loop size the path integral is dominated by the minimal-action sheet, so

$$
\langle W(C)\rangle
\sim \exp[-\sigma A_{\min}(C)].
$$

For a rectangular loop $A_{\min}=r\mathcal T$, giving

$$
\langle W(r,\mathcal T)\rangle\sim e^{-\sigma r\mathcal T},
\qquad
V(r)=\sigma r.
$$

</details>

## References

### Standard first pass

- A. M. Polyakov, *Gauge Fields and Strings*, ch. 4, for compact QED, monopole instantons, the monopole gas, and mass-gap generation.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, ch. 9, for compact QED in gauge-theory and condensed-matter contexts.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, ch. 9, for confinement mechanisms in lower-dimensional models and Polyakov's compact QED example.

### Deeper references

- A. M. Polyakov, “Quark Confinement and Topology of Gauge Theories,” for the original compact QED₃ confinement mechanism.
- T. Banks, R. Myerson, and J. Kogut, “Phase Transitions in Abelian Lattice Gauge Theories,” for the lattice monopole/Coulomb-gas treatment.
- J. Kogut, “An Introduction to Lattice Gauge Theory and Spin Systems,” for compact lattice gauge theory and Hamiltonian formulations.
- M. Peskin, “Mandelstam–’t Hooft Duality in Abelian Lattice Models,” for duality and loop-operator perspectives.

## Version history

- **2026-06-27:** Initial polished page. Added compact versus noncompact distinction, monopole gas, dual sine-Gordon derivation, mass gap, Wilson-loop domain-wall area law, dimensional caveats, matter caveats, and exercises.
