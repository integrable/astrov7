---
title: "Flux Tubes"
description: "Explains confining flux tubes as string-like states of gauge fields, their relation to Wilson loops and string tension, and the limits of the effective-string picture."
sidebar:
  label: "Flux Tubes"
  order: 6
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov; Srednicki ch. 82; Shifman chs. 1, 3, and 9; lattice flux-tube and effective-string literature."
topics:
  - flux tubes
  - confinement
  - string tension
  - Wilson loops
  - effective string theory
  - center symmetry
  - lattice gauge theory
canonicalTopics:
  - nonperturbative-qft
  - confinement
  - flux-tubes
  - string-tension
  - wilson-loops
researchStatus:
  established:
    - "A confining flux tube is the infrared field configuration sourced by unscreened probe charges, and its energy grows linearly with length when the corresponding string tension is nonzero."
  active:
    - "The detailed worldsheet dynamics of QCD-like flux tubes, including massive modes, k-strings, junctions, and universality beyond leading effective-string terms, remains an active nonperturbative topic."
---

## Summary

A **flux tube** is a state of the gauge-field vacuum in the presence of separated external charges. In a confining phase, color-electric flux does not spread throughout space like the electric field of ordinary Coulomb theory. Instead, the lowest-energy configuration localizes the flux into a tube of finite transverse thickness connecting the probes.

For static sources separated by distance $r$, the energy of a stable long tube has the asymptotic form

$$
E_0(r)=V(r)=
\sigma r+c+\text{subleading terms},
$$

where $\sigma$ is the [String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/). The linear term is the macroscopic statement that adding length costs a fixed amount of energy per unit length.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A static source and antisource connected by a localized color-electric flux tube, its Euclidean worldsheet, and the long-string effective-potential regime.](/figures/nonperturbative-qft/flux-tube-worldsheet-profile.svg)

<figcaption>

A long confining flux tube has three complementary descriptions: a localized field profile between static probes, a Wilson-loop worldsheet in Euclidean spacetime, and a long-string effective theory whose leading energy is $\sigma r$ plus subleading fluctuation effects.

</figcaption>
</figure>

The word “tube” should be taken seriously but not literally. A flux tube is not a classical rubber string inserted into the theory. It is a collective, gauge-invariant, nonperturbative excitation of the vacuum. At long distances it admits a string-like effective description; at distances comparable to its thickness it remembers the microscopic gauge theory.

## Prerequisites

You should know [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), [Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/), [String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/), and [Center Symmetry](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/).

For mechanisms, read [Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/) and [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) in parallel. They show two very different ways a Wilson-loop area law can arise: plaquette tiling on a lattice and monopole-induced mass generation in compact QED₃.

## Core idea

Imagine placing a heavy external quark and antiquark in a pure non-Abelian gauge theory. The charges themselves are probes; they are not dynamical light particles that can be pair-created to screen each other. The gauge field must arrange itself into a state compatible with the imposed color source and antisource.

In a Coulomb phase, the flux spreads. The energy grows slowly, for example like $1/r$ in four-dimensional electrodynamics. In a confining phase, the flux is squeezed into a tube. If the tube has roughly fixed transverse profile as its length grows, then its energy is extensive in length:

$$
E_{\mathrm{tube}}(r)
\approx
\int_0^r dz\,\varepsilon_{\mathrm{line}}
=\sigma r.
$$

This physical picture is the Hamiltonian version of the Wilson-loop area law. A rectangular Wilson loop of spatial size $r$ and Euclidean time size $\mathcal T$ creates two static sources, propagates them for time $\mathcal T$, and annihilates them. If the worldsheet swept out by the tube costs action proportional to its area, then

$$
\langle W(C_{r,\mathcal T})\rangle
\sim
\exp(-\sigma r\mathcal T),
$$

so

$$
V(r)
=-\lim_{\mathcal T\to\infty}\frac{1}{\mathcal T}
\log\langle W(C_{r,\mathcal T})\rangle
\sim \sigma r.
$$

Thus the flux-tube picture and the Wilson-loop area law are the same long-distance physics viewed from two sides.

## What is actually localized?

In a gauge theory, the phrase “electric field lines” is not itself a gauge-invariant local observable. The microscopic field strength $F_{\mu\nu}^a$ carries a color index, and $F_{\mu\nu}^aF^{a\mu\nu}$ is gauge invariant but does not directly draw individual color field lines. Still, one can define gauge-invariant measurements of the energy density or action density in the presence of a Wilson loop.

A typical lattice diagnostic is a connected correlator of a Wilson loop with a local plaquette or field-strength operator. Schematically,

$$
\delta \mathcal E(x;C)
=\frac{\langle W(C)\,\mathcal E(x)\rangle}{\langle W(C)\rangle}
-\langle\mathcal E(x)\rangle,
$$

where $\mathcal E$ is a gauge-invariant energy-density or action-density operator. In a confining regime, $\delta\mathcal E$ is enhanced in a tube-like region between the static sources.

The transverse profile is not universal at all distances. One may define a width $w(r)$ through a moment of the energy density,

$$
w^2(r)
=\frac{\int d^{d-2}x_\perp\,x_\perp^2\,\delta\mathcal E(x_\perp;r)}
{\int d^{d-2}x_\perp\,\delta\mathcal E(x_\perp;r)},
$$

but the precise operator and smearing procedure matter. The universal information appears only after separating short-distance operator details from long-distance string fluctuations.

## Long strings and transverse modes

A long flux tube spontaneously breaks translations transverse to its axis. If the only light degrees of freedom on the tube are the corresponding transverse oscillations, the infrared worldsheet theory contains $d-2$ massless scalar fields,

$$
X^i(\tau,z),
\qquad i=1,\dots,d-2,
$$

where $z$ is the coordinate along the tube and $\tau$ is Euclidean time. The leading action is the effective action for a fluctuating string. Expanding around a straight tube gives

$$
S_{\mathrm{ws}}
=\sigma\int d\tau dz
+\frac{\sigma}{2}\int d\tau dz\,\partial_\alpha X^i\partial^\alpha X^i
+\cdots.
$$

Quantizing these transverse modes gives universal subleading corrections to the ground-state energy. For an open string between static sources, the leading correction is the Lüscher term,

$$
V(r)=\sigma r+c
-\frac{\pi(d-2)}{24r}
+O\!\left(\frac{1}{r^3}\right),
$$

under the standard long-string assumptions. In four spacetime dimensions,

$$
V(r)=\sigma r+c-\frac{\pi}{12r}+\cdots.
$$

This correction is universal in the same modest sense as hydrodynamic universality: it follows from the massless long-wavelength modes and symmetries, not from the microscopic details of the gauge theory. Massive worldsheet modes, boundary terms, finite thickness, and mixing with broken-string states can modify nonleading behavior.

## Open, closed, and winding flux tubes

There are several related objects.

An **open flux tube** connects external static sources. It is the object extracted from rectangular Wilson loops and static potentials. Its endpoints are not ordinary dynamical particles unless the theory contains heavy matter fields.

A **closed flux tube** is a loop of confining flux with no endpoints. In a finite periodic box, a closed tube can wind around a spatial cycle. Such a winding flux tube is often called a **torelon**. Its energy at large length $L$ behaves roughly as

$$
E_{\mathrm{tor}}(L)
=\sigma L-\frac{\pi(d-2)}{6L}+\cdots,
$$

again when the effective-string description applies.

A **glueball** is not simply a small circular string, but the pictures are related. Glueballs are localized gauge-invariant excitations of the pure gauge vacuum. At large excitation number, or in [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) intuition, one often thinks of some glueball states as closed flux-tube excitations. For the lightest glueballs, the microscopic gauge dynamics is too important for a naive thin-string picture to be reliable.

A **$k$-string** is a flux tube carrying nontrivial center charge $k\in\mathbb Z_N$ in pure $SU(N)$ gauge theory. Its tension $\sigma_k$ is an asymptotic infrared quantity associated with N-ality. The ratios $\sigma_k/\sigma_1$ encode nontrivial nonperturbative information.

## Why center charge matters

In pure $SU(N)$ Yang–Mills theory, dynamical gluons transform in the adjoint representation. They can screen many representation-dependent details of a source, but they cannot change its charge under the center $\mathbb Z_N$. Therefore stable asymptotic electric flux tubes are classified by center charge, or N-ality, rather than by the full representation.

If $R$ has N-ality $k_R$, the asymptotic tube sourced by $R$ should belong to the $k_R$ sector. Representations with the same $k_R$ can differ at intermediate distances but flow to the same asymptotic string sector. Representations with $k_R=0$ can be screened by gluons and do not require a stable asymptotic string.

In a theory with dynamical fundamental matter, even center charge can be screened. A fundamental flux tube may form at intermediate distances, but at sufficiently large separation the energetically preferred state is often two screened heavy-light objects rather than one long tube. This is string breaking:

$$
V(r)\sim \sigma r
\quad\text{for intermediate }r,
\qquad
V(r)\to 2M_{Q\bar q}
\quad\text{as }r\to\infty.
$$

That is why the strict flux-tube order parameter is sharpest in pure gauge theory or in matter content that preserves the relevant one-form symmetry.

## Mechanisms that produce tubes

Different theories confine by different controlled mechanisms. The flux-tube language is a shared infrared description, not a universal microscopic explanation. The large-$N$ limit makes this description sharper by suppressing string splitting, joining, and quark-loop string breaking; see [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/).

In the **lattice strong-coupling expansion**, the leading nonzero contribution to a Wilson loop comes from plaquettes tiling a surface whose boundary is the loop. The cost is proportional to the number of plaquettes, so the Wilson loop obeys an area law. In Hamiltonian language, the external sources are connected by a string of excited links.

In **compact QED₃**, monopole instantons generate a mass for the dual photon. A Wilson loop imposes a discontinuity in the dual field; the minimal configuration is a domain-wall-like sheet ending on the loop. The sheet tension becomes the string tension, and the Hamiltonian picture is an electric flux tube.

In the **dual-superconductor picture** of non-Abelian confinement, magnetic degrees of freedom condense, and color-electric flux is squeezed into tubes by a dual Meissner effect. This is an extremely useful analogy, and it is realized sharply in some supersymmetric or Abelianized regimes. In ordinary four-dimensional Yang–Mills theory, identifying the precise gauge-invariant magnetic variables responsible for confinement is more subtle.

In **center-vortex pictures**, the vacuum contains extended magnetic defects whose linking with Wilson loops disorders the loop phase and produces area-law behavior. This is another useful mechanism proposal, with lattice and continuum variants. As with all confinement mechanisms, the key is to distinguish the controlled statement from the suggestive picture.

## Width, roughening, and universality

A flux tube has a microscopic core and long-distance fluctuations. These are different pieces of physics.

The core thickness is set by the inverse mass scale of the surrounding vacuum, roughly

$$
w_0\sim \Delta^{-1},
$$

where $\Delta$ is a relevant mass gap. This is not an exact equality; it is a dimensional and physical estimate.

The long string can also fluctuate. In many effective-string treatments, the mean-square width grows logarithmically with separation in four spacetime dimensions:

$$
w^2(r)
\sim
w_0^2+\frac{d-2}{2\pi\sigma}\log\frac{r}{r_0}
+\cdots.
$$

This “roughening” is an infrared fluctuation effect. It should not be confused with the microscopic thickness of the core. The distinction is a common source of muddled intuition: the tube can have a finite local core while its long-distance positional fluctuations broaden the measured profile.

## Flux tubes and the mass gap

Flux tubes and the mass gap are connected but not identical.

A stable tube has a tension, so $\sqrt{\sigma}$ is a mass scale. In pure Yang–Mills theory, glueball masses and flux-tube tensions are both expected to be of order the dynamically generated scale $\Lambda_{\mathrm{YM}}$. A typical dimensionless comparison is

$$
\frac{m_{0^{++}}}{\sqrt{\sigma}}.
$$

But the logic is not reversible in general. A theory can be gapped without confining probe charges. A Higgs phase can have massive particles and perimeter-law Wilson loops. A topological gauge theory can have finite correlation length for local operators while possessing nontrivial extended topological sectors. The flux tube is a confinement diagnostic; the mass gap is a spectral diagnostic.

## Common mistakes

**Mistake 1: Treating a flux tube as a literal fundamental string.** A confining flux tube may have a string-like infrared description, but it is made from gauge-field degrees of freedom.

**Mistake 2: Ignoring the thickness.** Effective string theory is a long-distance expansion. It cannot describe the tube core, the short-distance Coulomb regime, or the detailed field profile near the sources.

**Mistake 3: Forgetting string breaking.** In theories with dynamical matter in the right representations, the true ground state at very large separation can be a screened state rather than an unbroken tube.

**Mistake 4: Confusing representation dependence with N-ality dependence.** At intermediate distances, potentials can show approximate Casimir scaling. At asymptotically long distances in pure $SU(N)$ gauge theory, stable tubes are classified by center charge.

**Mistake 5: Overinterpreting one mechanism.** Strong-coupling plaquette tiling, compact-QED₃ monopoles, dual superconductivity, and center vortices teach different things. None is automatically a complete proof of ordinary four-dimensional Yang–Mills confinement.

## Research status

- **Established:** A Wilson-loop area law and a linearly rising static potential correspond to a flux tube with nonzero string tension in the relevant probe sector.
- **Established:** Lattice gauge theory provides direct evidence for flux-tube energy-density profiles, string tensions, and excited string spectra in pure non-Abelian gauge theories.
- **Established:** Long stable flux tubes have universal transverse fluctuation effects captured by effective string theory at sufficiently large separation.
- **Active:** The full worldsheet theory of QCD-like flux tubes, including massive modes and boundary effects, remains under investigation.
- **Active:** The dynamics of $k$-strings, baryonic junctions, large-$N$ scaling, and flux tubes in theories with matter continue to connect lattice, semiclassical, and holographic methods.

## Relations to other pages

[Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) derives the loop criterion whose Hamiltonian interpretation is the creation of a flux tube.

[String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/) defines the coefficient $\sigma$ that measures the tube energy per unit length.

[Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/) explains why some flux tubes break or become metastable when dynamical matter can screen the endpoints.

[Center Symmetry](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/) and [One-Form Symmetry and Confinement](/nonperturbative-qft/confinement-screening-mass-gap/one-form-symmetry-confinement/) explain the symmetry reason why pure gauge theory has stable center-charged strings.

[Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) gives a controlled mechanism where a monopole-generated dual-photon mass produces a confining string tension.

[Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) explains why flux-tube splitting and joining are suppressed in the large-$N$ limit, making the string picture sharper. [Confinement Mechanisms](/nonperturbative-qft/confinement-screening-mass-gap/confinement-mechanisms/) places the flux-tube effective string among other explanations such as strong coupling, monopole gases, dual superconductivity, and center vortices.

## Exercises

### Exercise 1: Tube energy from a fixed transverse profile

Suppose the energy density of a straight flux tube is translationally invariant along the tube direction $z$ and has transverse profile $\varepsilon(x_\perp)$. Show that the energy of a length-$r$ segment is

$$
E(r)=\sigma r,
\qquad
\sigma=\int d^{d-2}x_\perp\,\varepsilon(x_\perp).
$$

<details>
<summary><strong>Solution</strong></summary>

The total energy is the integral over the tube volume:

$$
E(r)=\int_0^r dz\int d^{d-2}x_\perp\,\varepsilon(x_\perp).
$$

The transverse integral is independent of $z$, so

$$
E(r)=r\int d^{d-2}x_\perp\,\varepsilon(x_\perp).
$$

Defining

$$
\sigma=\int d^{d-2}x_\perp\,\varepsilon(x_\perp)
$$

gives

$$
E(r)=\sigma r.
$$

</details>

### Exercise 2: Lüscher term in four dimensions

Use

$$
V(r)=\sigma r+c-\frac{\pi(d-2)}{24r}+\cdots
$$

for an open flux tube. What is the coefficient of the $1/r$ term in $d=4$ spacetime dimensions?

<details>
<summary><strong>Solution</strong></summary>

For $d=4$, the number of transverse directions is

$$
d-2=2.
$$

Therefore

$$
-\frac{\pi(d-2)}{24r}
=-\frac{2\pi}{24r}
=-\frac{\pi}{12r}.
$$

So the leading universal correction is

$$
V(r)=\sigma r+c-\frac{\pi}{12r}+\cdots.
$$

</details>

### Exercise 3: Why screening kills the asymptotic tube

A theory contains dynamical matter that can bind to each external source. The unbroken tube energy is $\sigma r$, while the screened two-particle state has energy $2M$. Estimate the separation at which string breaking becomes energetically favorable.

<details>
<summary><strong>Solution</strong></summary>

Compare the two energies:

$$
E_{\mathrm{tube}}(r)\approx \sigma r,
\qquad
E_{\mathrm{screen}}\approx 2M.
$$

String breaking becomes energetically favorable when

$$
\sigma r\gtrsim 2M.
$$

Thus a rough estimate is

$$
r_{\mathrm{br}}\sim \frac{2M}{\sigma}.
$$

In a real theory there are additive constants, mixing matrix elements, finite-volume effects, and excited-state issues. The estimate captures the basic energetic reason why a strict asymptotic tube cannot survive when the endpoints can be screened.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, chapter 82, for Wilson loops, lattice gauge theory, area laws, string tension, and confinement diagnostics.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong-coupling expansion, compact QED, confinement analogies, loop dynamics, large-$N$ expansion, and random surfaces.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on vortices and flux tubes, phases of gauge theories, and confinement in lower-dimensional models.

### Deeper references

- M. Lüscher, K. Symanzik, and P. Weisz, and later effective-string literature, for universal long-string corrections and flux-tube spectroscopy.
- J. Greensite, *An Introduction to the Confinement Problem*, for lattice evidence, center vortices, string breaking, and flux-tube diagnostics.
- B. Lucini and M. Panero’s large-$N$ lattice reviews, for $k$-strings, torelons, glueballs, and large-$N$ scaling of flux-tube data.

## Version history

- **2026-06-27:** Initial polished page. Added flux-tube definition, gauge-invariant profile measurements, effective-string expansion, open and closed tubes, N-ality, string breaking, mechanisms, roughening, and exercises.
- **2026-06-27:** Added link to Large-N Confinement for the planar/string organization of stable tubes.

