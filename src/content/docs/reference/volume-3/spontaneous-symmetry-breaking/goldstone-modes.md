---
title: "Goldstone Modes"
description: "Explains what Goldstone modes are, how they appear as long-wavelength collective coordinates of a broken continuous symmetry, and how their counting, dispersion, normalization, and low-energy interactions work in relativistic and nonrelativistic settings."
sidebar:
  label: "Goldstone Modes"
  order: 4
level: Graduate
status: "Polished draft"
source: "Goldstone; Goldstone–Salam–Weinberg; Coleman on secret symmetry and soft pions; Srednicki §§30–32; Schwartz Ch. 28; Weinberg Vol. II; Watanabe–Murayama on nonrelativistic counting."
topics:
  - Goldstone modes
  - Nambu–Goldstone bosons
  - spontaneous symmetry breaking
  - current algebra
  - decay constants
  - low-energy effective theory
  - type-A Goldstone modes
  - type-B Goldstone modes
canonicalTopics:
  - goldstone-mode
  - nambu-goldstone-boson
  - decay-constant
  - type-a-goldstone
  - type-b-goldstone
  - goldstone-counting
  - low-energy-mode
researchStatus:
  established:
    - "For exact continuous internal symmetry breaking in a Lorentz-invariant vacuum, the Goldstone excitations are gapless spin-zero modes, one per broken generator under the standard assumptions."
    - "The leading low-energy dynamics of Goldstone modes is governed by symmetry and derivative interactions rather than by details of the ultraviolet Lagrangian."
  active:
    - "Goldstone counting, dispersion, and effective actions remain especially subtle for finite-density systems, spacetime symmetries, generalized symmetries, open systems, long-range forces, and systems coupled to dynamical gauge fields."
---

## Summary

A **Goldstone mode** is the long-wavelength excitation that moves a system along a continuously degenerate family of symmetry-related vacua. It is not merely a massless particle that happens to be light. It is the local, slowly varying version of the statement that the vacuum manifold has a flat symmetry direction.

For ordinary internal symmetry breaking

$$
G\longrightarrow H,
$$

the broken generators span the tangent directions of the coset space $G/H$. In a relativistic vacuum, each broken generator gives one massless spin-zero mode, conventionally written $\pi^a(x)$, and the broken current creates that mode from the vacuum:

$$
\langle\Omega|j_A^\mu(0)|\pi_B(p)\rangle
=
iF_{AB}p^\mu.
$$

The matrix $F_{AB}$ is a decay-constant matrix. It measures how strongly the current overlaps with the Goldstone one-particle state. With standard normalizations, current conservation and Lorentz invariance force the mode to be gapless:

$$
p_\mu\langle\Omega|j_A^\mu(0)|\pi_B(p)\rangle
=
iF_{AB}p^2
=0
\quad\Longrightarrow\quad
p^2=0
$$

when $F_{AB}\ne0$.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A diagram summarizing Goldstone-mode counting. A broken internal symmetry G to H gives broken generators and fields pi^a. In a Lorentz-invariant vacuum rho equals zero, so the number of Goldstone modes equals the number of broken generators and the dispersion is linear. At finite density or in nonrelativistic matter rho can be nonzero, causing pairs of broken generators to make type-B modes. Both feed into low-energy EFT data.](/figures/symmetry-anomalies-topology/goldstone-mode-counting-map.svg)

<figcaption>

Goldstone modes are tangent coordinates on the vacuum manifold, but their dynamics depends on the state. In a Lorentz-invariant vacuum, the charge-commutator density $\rho_{ab}$ vanishes and there is one linear Goldstone mode per broken internal generator. At finite density or in nonrelativistic matter, $\rho_{ab}$ can have nonzero rank, pairing broken charges into type-B modes.

</figcaption>
</figure>

The simplest slogan is:

$$
\text{Goldstone mode}
=
\text{slow motion along }G/H.
$$

The better slogan is:

$$
\text{Goldstone mode}
=
\text{the infrared carrier of a broken charge}.
$$

That second version remembers the Ward identity, the current pole, and the possibility that counting and dispersion change outside the relativistic internal-symmetry setting.

## Prerequisites

Read [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/) and [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/) first. You should also know [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/), [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/), and [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/).

For the effective-theory parts, it helps to know the idea of a derivative expansion. The next page, [Coset Construction Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coset-construction-preview/), systematizes the geometry behind the formulas used here.

## Core idea

Suppose a continuous internal symmetry group $G$ is spontaneously broken to a subgroup $H$. The unbroken subgroup is the stabilizer of the selected vacuum:

$$
H=\{g\in G\mid U(g)|\Omega\rangle\text{ is physically the same vacuum}\}.
$$

The broken directions are represented by generators $X_a\in\mathfrak g/\mathfrak h$. Acting with a constant broken transformation moves the vacuum to another symmetry-related vacuum:

$$
|\Omega(\epsilon)\rangle
=
e^{i\epsilon^aQ_a}|\Omega\rangle.
$$

A Goldstone mode is obtained by letting that transformation vary slowly in spacetime:

$$
\epsilon^a\quad\rightsquigarrow\quad \pi^a(x)/f.
$$

A constant $\pi^a$ costs no energy because it only chooses another vacuum. Therefore the effective action cannot contain an ordinary potential for $\pi^a$ when the symmetry is exact. The leading terms must contain derivatives:

$$
\mathcal L_{\text{eff}}
=
\frac12 g_{ab}(\pi)\partial_\mu\pi^a\partial^\mu\pi^b
+O(\partial^4).
$$

The absence of a potential is not a tuning. It is enforced by the nonlinear symmetry inherited from $G$.

## Setup and conventions

We use the volume's mostly-minus metric and the charge convention

$$
\delta_A\mathcal O=i[Q_A,\mathcal O].
$$

For a broken current $j_A^\mu$, the Goldstone matrix element is written

$$
\langle\Omega|j_A^\mu(0)|\pi_B(p)\rangle=iF_{AB}p^\mu.
$$

This fixes a common sign convention for the decay constants. Some references absorb the $i$ into state or current conventions, especially after Wick rotation. The physical content is the residue of the massless current pole, not the isolated factor of $i$.

We write the number of broken internal generators as

$$
n_{\text{broken}}=\dim G-\dim H.
$$

In a Lorentz-invariant relativistic vacuum,

$$
n_{\rm NG}=n_{\text{broken}}.
$$

In nonrelativistic systems or finite-density states, the more general internal-symmetry counting formula is

$$
n_{\rm NG}
=
n_{\text{broken}}-\frac12\operatorname{rank}\rho,
\qquad
\rho_{ab}
=
-\frac{i}{V}\langle[Q_a,Q_b]\rangle.
$$

Here $V$ is spatial volume, and $\rho_{ab}$ is the charge-commutator density in the selected state. This formula is a statement about internal symmetries under standard locality and regularity assumptions. Spacetime symmetries require additional care.

:::note[Convention-sensitive source note]
The sign in $\rho_{ab}$ follows the charge-action convention above. If a source uses $\delta_A\mathcal O=-i[Q_A,\mathcal O]$, or defines Lie-algebra generators with the opposite Hermiticity convention, the displayed sign changes. The rank of $\rho$ and the counting formula do not.
:::

## Goldstone fields as coordinates on the vacuum manifold

The vacuum manifold is locally modeled by

$$
\mathcal M_{\text{vac}}\simeq G/H.
$$

A Goldstone field is a coordinate on this manifold. For an $O(N)$ model with real scalars $\phi^i$ and a vacuum expectation value in the $N$th direction,

$$
\langle\phi^i\rangle=v\delta^{iN},
$$

the symmetry breaking pattern is

$$
O(N)\longrightarrow O(N-1).
$$

The vacuum manifold is

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

At low energy, the massive radial fluctuation is expensive, while motion along the sphere is cheap. A useful parametrization is

$$
\phi^i(x)=\big(v+\sigma(x)\big)n^i(x),
\qquad
n^i n^i=1.
$$

The field $\sigma$ moves away from the vacuum manifold. The fields inside $n^i(x)$ move along it. At energies small compared with the radial mass, one integrates out $\sigma$ and obtains the nonlinear sigma model

$$
\mathcal L_{\text{eff}}
=
\frac{f^2}{2}\partial_\mu n^i\partial^\mu n^i+\cdots,
\qquad
n^i n^i=1.
$$

The dots denote higher-derivative terms and possible explicit-breaking terms. The number of independent components of $n^i$ is $N-1$, exactly the number of broken generators.

The crucial point is geometric: the light fields are not the components of the original microscopic field. They are coordinates on the space of vacua.

## Why the mass term is absent

A free relativistic scalar has Lagrangian

$$
\mathcal L=\frac12\partial_\mu\pi\partial^\mu\pi-\frac12m^2\pi^2.
$$

For a Goldstone mode of an exact internal symmetry, the mass term is forbidden. Locally near the origin of field space, the broken symmetry acts as a shift plus nonlinear corrections:

$$
\pi^a(x)\mapsto \pi^a(x)+f\epsilon^a+O(\pi\epsilon).
$$

A term $m^2\pi^a\pi^a$ is not invariant under the shift. A derivative term is invariant under constant shifts:

$$
\partial_\mu\pi^a\mapsto \partial_\mu\pi^a+O(\pi\partial\epsilon,\epsilon\partial\pi).
$$

For a global transformation, $\partial_\mu\epsilon^a=0$, so constant shifts cost no energy. This is the field-theory version of moving from one point on $G/H$ to another.

This is why Goldstone bosons are naturally light. Their masslessness is protected by symmetry. To give them a small mass, one must either explicitly break the symmetry, gauge the symmetry, couple to long-range forces in a way that changes the assumptions, or otherwise leave the setting of the theorem.

## Decay constants and current normalization

Goldstone modes are detected by currents. The basic current matrix element is

$$
\langle\Omega|j_A^\mu(0)|\pi_B(p)\rangle=iF_{AB}p^\mu.
$$

If the broken currents and Goldstone states are chosen in a convenient basis, $F_{AB}$ may be diagonal:

$$
F_{AB}=f_A\delta_{AB}.
$$

The constants $f_A$ depend on how the currents and fields are normalized. They are not all fixed by symmetry. For pions in QCD, the analog of $f_A$ is the pion decay constant $f_\pi$, a physical normalization appearing in weak matrix elements and chiral perturbation theory.

The pole in the current-current correlator has residue controlled by these constants. Schematically,

$$
\langle j_A^\mu(p)j_B^\nu(-p)\rangle
\supset
\frac{F_{AC}F_{BC}p^\mu p^\nu}{p^2+i\epsilon}.
$$

This formula hides contact terms and scheme-dependent local pieces, but the massless pole and its residue are physical in the broken phase.

:::note[Current normalization]
If the generator normalization changes, $T_A\mapsto c_AT_A$, then $j_A^\mu$ and $Q_A$ change by the same factor. The decay constant $F_{AB}$ changes accordingly. Statements such as "there is a pole" and "how many independent Goldstone modes exist" are invariant; numerical values of $f_A$ require a generator convention.
:::

## Dispersion in relativistic theories

In a Lorentz-invariant vacuum, a Goldstone boson has the low-momentum dispersion

$$
E^2=\mathbf p^2+O(|\mathbf p|^4/\Lambda^2),
$$

where the speed of light is set to one and $\Lambda$ is the scale where the Goldstone EFT breaks down. Lorentz invariance organizes the kinetic term as

$$
\frac12F_{ab}^2\partial_\mu\pi^a\partial^\mu\pi^b.
$$

After diagonalizing and canonically normalizing the fields, the leading equation of motion is

$$
\Box\pi^a=0.
$$

Thus the excitations are gapless and linearly dispersing:

$$
E=|\mathbf p|+
O(|\mathbf p|^3/\Lambda^2).
$$

A derivative expansion can correct the dispersion at higher order, but it cannot generate a gap while the symmetry remains exact and the assumptions remain valid.

## Type-A and type-B modes

In relativistic vacua, the phrase "one Goldstone boson per broken generator" is usually safe. In many-body systems it is not.

Let $Q_a$ and $Q_b$ be broken charges. If their commutator has a nonzero expectation-value density,

$$
\rho_{ab}=-\frac{i}{V}\langle[Q_a,Q_b]\rangle\ne0,
$$

then the two broken directions can be canonically conjugate. Instead of producing two independent Goldstone modes, they can produce one mode. The general internal-symmetry counting rule is

$$
n_{\rm NG}=n_{\text{broken}}-\frac12\operatorname{rank}\rho.
$$

One also often separates modes into type-A and type-B modes:

$$
n_{\rm A}+2n_{\rm B}=n_{\text{broken}},
\qquad
n_{\rm B}=\frac12\operatorname{rank}\rho,
$$

under the same standard assumptions. Type-A modes are associated with unpaired broken generators. Type-B modes are associated with paired broken generators. In many familiar nonrelativistic systems, type-A modes have linear dispersion and type-B modes have quadratic dispersion, but the symmetry statement is the counting; dispersion can be affected by additional spacetime symmetries, long-range interactions, and dynamical assumptions.

### Ferromagnet versus antiferromagnet

A ferromagnet breaks spin rotation symmetry

$$
SU(2)\longrightarrow U(1).
$$

There are two broken generators, say $S_x$ and $S_y$. But in a ferromagnetic state,

$$
[S_x,S_y]=iS_z,
\qquad
\langle S_z\rangle/V\ne0.
$$

Therefore $\rho_{xy}\ne0$ and the two broken generators form one canonically conjugate pair. The low-energy theory has one magnon mode, commonly with quadratic dispersion.

An antiferromagnet can have the same symmetry breaking pattern, but the uniform spin density vanishes:

$$
\langle S_z\rangle/V=0.
$$

Then $\rho=0$ and there are two Goldstone modes, commonly with linear dispersion. The group-theoretic breaking pattern alone is not enough; the state matters.

## Examples

### Broken U(1) symmetry

A complex scalar with potential

$$
V(\Phi)=\frac{\lambda}{4}\left(2\Phi^\dagger\Phi-v^2\right)^2
$$

has a $U(1)$ symmetry

$$
\Phi\mapsto e^{-i\alpha}\Phi.
$$

Choose a vacuum

$$
\langle\Phi\rangle=\frac{v}{\sqrt2}.
$$

A useful parametrization is

$$
\Phi(x)=\frac{v+\sigma(x)}{\sqrt2}e^{i\pi(x)/f}.
$$

The radial field $\sigma$ is massive. The phase field $\pi$ is the Goldstone mode. At low energies,

$$
\mathcal L_{\text{eff}}
=\frac12\partial_\mu\pi\partial^\mu\pi+O(\partial^4).
$$

The action depends only on derivatives of $\pi$, reflecting the shift symmetry

$$
\pi\mapsto \pi+f\alpha.
$$

### Chiral symmetry breaking

For $N_f$ light quark flavors, the approximate chiral symmetry of QCD is often summarized as

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V.
$$

The associated Goldstone modes are the pseudoscalar mesons. For $N_f=2$, these are the three pions in the idealized chiral limit. For $N_f=3$, one gets an octet in the idealized limit. In real QCD the light quark masses explicitly break the symmetry, so the pions, kaons, and eta are pseudo-Goldstone bosons rather than exactly massless particles.

The low-energy field is commonly written

$$
U(x)=e^{2i\pi^a(x)T^a/f_\pi},
\qquad
U(x)\in SU(N_f),
$$

and the leading chiral Lagrangian is

$$
\mathcal L_2
=\frac{f_\pi^2}{4}\operatorname{tr}\big(\partial_\mu U^\dagger\partial^\mu U\big).
$$

This is a canonical example of symmetry determining infrared dynamics.

### Superfluids

A neutral superfluid breaks a global particle-number $U(1)$ symmetry. The Goldstone mode is the superfluid phase, often called the phonon. Its leading effective action is constrained by the shift symmetry of the phase and by spacetime symmetries appropriate to the medium.

Unlike a relativistic vacuum, a superfluid selects a rest frame and a finite density. Therefore the speed of the Goldstone mode is the sound speed, not the speed of light:

$$
E=c_s|\mathbf p|+\cdots.
$$

The mode is still Goldstone because it is the long-wavelength phase fluctuation associated with broken $U(1)$.

## Interactions are derivative and soft

Goldstone interactions are weak at low momentum. The reason is not small coupling in the ultraviolet; it is symmetry. Since a constant Goldstone field just moves the vacuum along $G/H$, interactions must involve derivatives.

For a single Goldstone mode with an approximate shift symmetry, a schematic effective Lagrangian is

$$
\mathcal L_{\text{eff}}
=\frac12(\partial\pi)^2
+\frac{c_4}{\Lambda^4}(\partial\pi)^4
+\frac{c_6}{\Lambda^8}(\partial\pi)^6
+\cdots.
$$

Tree-level scattering amplitudes vanish as external momenta are taken soft. In pion physics this is the origin of Adler-zero behavior in appropriate amplitudes. In the general case, soft behavior can be modified by explicit breaking, Wess–Zumino terms, anomalies, spacetime symmetry breaking, or singular infrared effects, but derivative coupling is the default internal-symmetry expectation.

## Goldstone modes and long-range correlations

Massless modes produce long-range correlations. In a relativistic theory in $d$ spacetime dimensions, a free massless scalar has two-point behavior roughly

$$
\langle\pi(x)\pi(0)\rangle\sim\frac{1}{|x|^{d-2}}
$$

for $d>2$, up to normalization and signature choices. Derivatives decay faster:

$$
\langle\partial\pi(x)\partial\pi(0)\rangle\sim\frac{1}{|x|^{d}}.
$$

This matters because many physical observables are built from derivatives or exponentials of Goldstone fields. In low dimensions, Goldstone fluctuations can become so large that ordinary long-range order is destroyed. That is the physics behind the Coleman–Mermin–Wagner warning developed later in the chapter.

## What happens when the symmetry is explicitly broken?

If the symmetry is not exact, the Goldstone mode is no longer protected from a mass. Suppose a small parameter $\epsilon$ explicitly breaks $G$. Then the effective Lagrangian may contain a potential

$$
V_{\text{eff}}(\pi)=\epsilon f^4\,\mathcal V(\pi/f).
$$

Expanding near its minimum gives

$$
V_{\text{eff}}(\pi)=\frac12m_\pi^2\pi^2+\cdots,
\qquad
m_\pi^2\propto \epsilon.
$$

The resulting particle is a **pseudo-Goldstone boson**. It is light because its mass is controlled by the small explicit-breaking parameter. Pions in real-world QCD are the standard example: they are much lighter than generic hadrons because light-quark masses softly break chiral symmetry.

## What happens when the symmetry is gauged?

If the broken symmetry is promoted to a dynamical gauge redundancy, the ordinary Goldstone particle may disappear from the physical spectrum. In the abelian Higgs model, the phase field that would be a Goldstone boson for a global $U(1)$ becomes the longitudinal polarization of a massive gauge boson.

This is often described as the gauge field "eating" the Goldstone mode. The phrase is vivid but slightly dangerous. Gauge symmetry itself is not a physical global symmetry that breaks in the same sense. The physical statement is that the spectrum reorganizes: a massless gauge boson with two transverse polarizations plus a scalar phase mode becomes a massive vector with three polarizations in four spacetime dimensions.

Gauge-invariant diagnostics are discussed later in [Higgs Mechanism Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/higgs-mechanism-preview/) and in the [Gauge Redundancy and BRST](/symmetry-anomalies-topology/gauge-redundancy-brst/) chapter.

## Spacetime symmetry breaking warning

For internal symmetries, broken generators are often a good first count of Goldstone fields. For spacetime symmetries, this can fail dramatically.

A crystal breaks spatial translations and rotations, but its low-energy elastic theory has phonons associated primarily with broken translations. Broken rotations do not give independent rotational Goldstone fields in the ordinary low-energy description. Their effects are encoded in derivatives of the displacement fields. This is one manifestation of the inverse-Higgs phenomenon.

A superfluid breaks particle number, boosts, and time translations in a state-dependent way, but its low-energy spectrum contains one phonon, not one independent mode for every naively broken generator.

The lesson is simple:

$$
\text{spacetime symmetry breaking requires spacetime kinematics.}
$$

The coset construction can handle many such examples, but it needs extra structure beyond the internal-symmetry story.

## Common pitfalls

**“A Goldstone mode is just a massless scalar.”** A Goldstone mode is massless because it carries a broken continuous symmetry. A massless scalar not protected by symmetry can usually be gapped by a small allowed mass term.

**“The Goldstone field is always the original field in the Lagrangian.”** Often it is a phase, angle, displacement, or composite collective coordinate. In chiral symmetry breaking, the pions are not fundamental elementary scalar fields in the ultraviolet QCD Lagrangian.

**“One broken generator always means one mode.”** This is true in the standard relativistic internal-symmetry setting. Finite density, nonrelativistic systems, and spacetime symmetry breaking require refined counting.

**“Quadratic dispersion means the mode is not Goldstone.”** Ferromagnetic magnons are Goldstone modes even though their dispersion is commonly quadratic. Gaplessness and symmetry origin are the key points.

**“Derivative coupling means no interactions.”** Goldstone bosons interact, but their interactions vanish at sufficiently low momentum. Derivative interactions can still produce important finite-energy scattering and nontrivial nonlinear dynamics.

**“Gauge theories literally break gauge symmetry.”** Gauge fixing may make a Goldstone field visible or invisible depending on the gauge. Physical statements should be phrased in terms of gauge-invariant spectra and observables.

## Relations to other pages

- [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/) proves why massless current poles must appear.
- [Coset Construction Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coset-construction-preview/) explains how to build the Goldstone effective action from $G/H$.
- [Explicit versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/) distinguishes exact Goldstones from pseudo-Goldstones.
- [Pseudo-Goldstone Bosons](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/pseudo-goldstone-bosons/) develops the small-mass case.
- [Coleman–Mermin–Wagner Theorem Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coleman-mermin-wagner-theorem-preview/) explains the low-dimensional infrared caveat.
- [Higgs Mechanism Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/higgs-mechanism-preview/) explains how Goldstone degrees of freedom reorganize when a symmetry is gauged.
- [Anomalies and Boundaries](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-boundaries/) later explains how Goldstone fields can carry anomaly inflow data through Wess–Zumino terms.

## Research status

The relativistic internal-symmetry Goldstone story is settled textbook QFT. The Ward-identity proof, current matrix elements, and derivative low-energy interactions are standard.

The refined theory of Goldstone counting in nonrelativistic systems and finite-density states is also well established, with the rank formula for internal symmetries now part of the standard modern toolkit. Applications to spacetime symmetry breaking, open systems, higher-form symmetries, fracton-like systems, and non-invertible symmetry remain more context-dependent and are active areas of research.

There is also an important practical frontier: determining the correct Goldstone EFT for a real material, a dense phase of QCD, a cold-atom system, or a theory with anomalies often requires both symmetry and microscopic input.

## Exercises

### Exercise 1: Counting Goldstone modes in an O(N) model

Consider a relativistic $O(N)$ scalar theory with a vacuum expectation value

$$
\langle\phi^i\rangle=v\delta^{iN}.
$$

Find the unbroken subgroup and the number of Goldstone modes.

<details><summary><strong>Solution</strong></summary>

The unbroken transformations preserve the vector $\delta^{iN}$. They rotate only the first $N-1$ components, so

$$
O(N)\longrightarrow O(N-1).
$$

The number of broken generators is

$$
\dim O(N)-\dim O(N-1)
=\frac{N(N-1)}2-\frac{(N-1)(N-2)}2
=N-1.
$$

In a Lorentz-invariant vacuum, there is one Goldstone boson per broken internal generator. Thus

$$
n_{\rm NG}=N-1.
$$

</details>

### Exercise 2: Ferromagnetic counting

A ferromagnet has spin symmetry $SU(2)$ broken to rotations around the $z$ axis. The broken charges are $S_x$ and $S_y$, and the state has nonzero magnetization density $\langle S_z\rangle/V=M\ne0$. Use the rank formula to count the Goldstone modes.

<details><summary><strong>Solution</strong></summary>

The commutator is

$$
[S_x,S_y]=iS_z.
$$

Therefore

$$
\rho_{xy}=-\frac{i}{V}\langle[S_x,S_y]\rangle
=\frac{\langle S_z\rangle}{V}=M.
$$

The antisymmetric $2\times2$ matrix $\rho_{ab}$ has rank $2$ when $M\ne0$. There are two broken generators, so

$$
n_{\rm NG}
=2-\frac12(2)=1.
$$

The two broken generators form one canonical pair, giving one type-B Goldstone mode.

</details>

### Exercise 3: Why a mass term is forbidden

Let a single Goldstone field transform at leading order as

$$
\pi(x)\mapsto\pi(x)+f\alpha
$$

for constant $\alpha$. Show that $\frac12m^2\pi^2$ is forbidden but $\frac12\partial_\mu\pi\partial^\mu\pi$ is allowed.

<details><summary><strong>Solution</strong></summary>

Under the shift,

$$
\frac12m^2\pi^2
\mapsto
\frac12m^2(\pi+f\alpha)^2
=\frac12m^2\pi^2+m^2f\alpha\pi+\frac12m^2f^2\alpha^2.
$$

This is not equal to the original Lagrangian up to a total derivative, so the mass term is not invariant.

For the kinetic term,

$$
\partial_\mu\pi\mapsto\partial_\mu\pi+f\partial_\mu\alpha.
$$

Because $\alpha$ is constant for a global symmetry, $\partial_\mu\alpha=0$. Hence

$$
\frac12\partial_\mu\pi\partial^\mu\pi
$$

is invariant under the leading shift.

</details>

### Exercise 4: Decay constant from the effective current

Suppose the leading effective Lagrangian for a single Goldstone field is

$$
\mathcal L=\frac12\partial_\mu\pi\partial^\mu\pi,
$$

and the broken symmetry acts as $\delta\pi=f\alpha$. Find the leading Noether current and verify the one-particle matrix element has the form $i f p^\mu$ up to state-normalization convention.

<details><summary><strong>Solution</strong></summary>

For a local parameter $\alpha(x)$,

$$
\delta\pi=f\alpha(x).
$$

The variation of the Lagrangian is

$$
\delta\mathcal L
=\partial_\mu\pi\partial^\mu(f\alpha)
=f\partial_\mu\pi\partial^\mu\alpha.
$$

Using the standard localization definition, the coefficient of $\partial_\mu\alpha$ is the current:

$$
j^\mu=f\partial^\mu\pi.
$$

For a canonically normalized scalar field,

$$
\langle\Omega|\pi(0)|p\rangle=1
$$

in the common relativistic convention where external normalization factors are suppressed. Therefore

$$
\langle\Omega|j^\mu(0)|p\rangle
=f\langle\Omega|\partial^\mu\pi(0)|p\rangle
=i f p^\mu,
$$

up to the convention for plane waves and state normalization. The invariant content is that the current matrix element is proportional to $p^\mu$ with coefficient $f$.

</details>

## References

- J. Goldstone, “Field Theories with Superconductor Solutions,” *Nuovo Cimento* **19** (1961) 154–164.
- J. Goldstone, A. Salam, and S. Weinberg, “Broken Symmetries,” *Physical Review* **127** (1962) 965–970.
- Sidney Coleman, *Aspects of Symmetry*, especially “Secret Symmetry” and “Soft Pions.” Classic lecture treatment of spontaneous symmetry breaking, Goldstone bosons, and current algebra.
- Mark Srednicki, *Quantum Field Theory*, §§30–32. Standard graduate discussion of spontaneous symmetry breaking and continuous symmetries.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 28. Clear modern textbook treatment of SSB, Goldstone bosons, and the Higgs mechanism.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II. Detailed discussion of effective actions, broken symmetries, and Goldstone bosons.
- H. B. Nielsen and S. Chadha, “On How to Count Goldstone Bosons,” *Nuclear Physics B* **105** (1976) 445–453.
- H. Watanabe and H. Murayama, “Unified Description of Nambu–Goldstone Bosons without Lorentz Invariance,” *Physical Review Letters* **108** (2012) 251602.
- H. Watanabe, “Counting Rules of Nambu–Goldstone Modes,” *Annual Review of Condensed Matter Physics* **11** (2020) 169–187.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially Chs. 4 and 14. Effective-theory perspective on symmetries, nonlinear realization, and many-body Goldstone modes.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, chapters on broken symmetry, collective phenomena, and topological field theory.

## Version history

- 2026-06-17: First polished draft. Added the geometric definition of Goldstone modes, decay-constant conventions, relativistic dispersion, type-A/type-B counting, examples, gauge and spacetime caveats, exercises, and the Goldstone-mode counting figure.
