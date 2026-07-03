---
title: "Area Law and Perimeter Law"
description: "Explains how large Wilson and ’t Hooft loops distinguish area, perimeter, Coulomb, and screened behavior, and how these laws translate into static potentials."
sidebar:
  label: "Area and Perimeter Laws"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §82; Polyakov, Gauge Fields and Strings, Chs. 5 and 7; Schwartz Chs. 25–26; Gaiotto–Kapustin–Seiberg–Willett 2015."
topics:
  - area law
  - perimeter law
  - Wilson loops
  - ’t Hooft loops
  - confinement
  - screening
canonicalTopics:
  - area-law
  - perimeter-law
  - static-potential
  - string-tension
  - screening
researchStatus:
  established:
    - "Area and perimeter laws are standard large-loop diagnostics; for rectangular Wilson loops, an area law gives a linearly rising static potential for external probes."
  active:
    - "The interpretation of loop laws in theories with dynamical matter, mixed phases, finite temperature, and nontrivial line-operator spectra remains subtle and context-dependent."
---

## Summary

The **area law** and **perimeter law** describe how an extended line operator decays when its contour becomes large. For a large loop $C$, a Wilson loop or ’t Hooft loop may behave schematically as

$$
\langle L(C)\rangle\sim e^{-\sigma A_{\min}(C)}
\qquad\text{or}\qquad
\langle L(C)\rangle\sim e^{-\mu P(C)}.
$$

Here $A_{\min}(C)$ is the minimal area spanned by the loop and $P(C)$ is its perimeter. The coefficient $\sigma$ is a string tension when the area law describes a stable flux tube. The coefficient $\mu$ contains boundary and self-energy contributions, including ultraviolet divergences for bare line operators.

For a large rectangular Wilson loop $C_{R,T}$,

$$
\langle W(C_{R,T})\rangle\sim e^{-T V(R)},
\qquad T\to\infty.
$$

An area law gives $V(R)\sim \sigma R$. A perimeter law, after subtracting static-source self-energies, means the potential does not grow linearly at asymptotically large $R$. This is the practical bridge between Euclidean loop expectation values and confinement diagnostics.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![A large loop decomposed into perimeter and area terms, a rectangular Wilson loop extracting the static potential, and diagnostic outcomes for area, perimeter, and Coulomb behavior.](/figures/gauge-theories-standard-model/area-perimeter-diagnostics.svg)

<figcaption>

The large-loop exponent separates local line terms from infrared surface terms. A perimeter contribution is supported near $C$ and includes static-source self-energy, while an area contribution fills a spanning surface and gives a string tension. For a rectangle $R\times T$, the area term $\sigma RT$ becomes the linear static potential $V(R)=\sigma R$.

</figcaption>
</figure>

## Prerequisites

You should know [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/) and [’t Hooft Loops](/gauge-theories-standard-model/wilson-loops-confinement/thooft-loops/). The pages [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/) and [Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/) explain why a non-Abelian gauge theory can generate a physical infrared scale from a dimensionless coupling.

A first pass does not require detailed lattice gauge theory. The strong-coupling lattice argument below is included because it is the cleanest way to see an area law appear by direct counting.

## Core idea

Large loop laws separate **bulk cost** from **boundary cost**.

A perimeter law says the cost of the loop is localized near the line:

$$
-\log\langle L(C)\rangle \sim \mu P(C).
$$

That is what one expects when the line operator is screened or when its dominant energy is a self-energy of the external probe.

An area law says the loop forces the theory to pay for a two-dimensional sheet spanning the loop:

$$
-\log\langle L(C)\rangle \sim \sigma A_{\min}(C).
$$

That is what one expects when the line creates a flux tube or domain sheet whose energy is proportional to its worldsheet area. For a rectangular Wilson loop, this worldsheet is the Euclidean history of an electric flux tube stretched between external charges.

The distinction is simple but brutal: under a rescaling $C\mapsto C_L$, perimeter scales as $L$, area as $L^2$. For large enough loops, an area law is not a small correction. It is the main event.

## Setup and conventions

Let $L(C)$ denote a renormalized line operator supported on a smooth closed loop $C$. It may be a Wilson loop, a ’t Hooft loop, or a dyonic Wilson–’t Hooft loop. For a one-parameter family of large loops $C_L$ obtained by scaling a fixed shape by $L$, the two basic asymptotics are

$$
-\log\langle L(C_L)\rangle
=\sigma A_{\min}(C_L)+o(L^2)
$$

for an area law, and

$$
-\log\langle L(C_L)\rangle
=\mu P(C_L)+o(L)
$$

for a perimeter law.

A more honest expansion often contains both terms:

$$
-\log\langle L(C)\rangle
=\sigma A_{\min}(C)+\mu P(C)+\sum_i \Gamma_i(\theta_i)\log(\Lambda)+\cdots.
$$

The perimeter term includes line self-energies. If the loop has cusps with angles $\theta_i$, additional cusp divergences can appear. For phase diagnostics, one is usually interested in whether the **renormalized large-loop behavior** contains a nonzero area coefficient $\sigma$.

For a rectangular Wilson loop $C_{R,T}$ in Euclidean signature,

$$
P(C_{R,T})=2(R+T),
\qquad
A_{\min}(C_{R,T})=RT.
$$

The static potential is extracted by

$$
V(R)=-\lim_{T\to\infty}\frac{1}{T}\log\langle W(C_{R,T})\rangle,
$$

with the ultraviolet self-energy of the two long external worldlines subtracted when quoting a physical potential.

## Area law gives a linear potential

Suppose the rectangular Wilson loop has the asymptotic behavior

$$
\langle W(C_{R,T})\rangle
\sim \exp[-\sigma RT-\mu 2(R+T)+\cdots].
$$

Then

$$
-\frac{1}{T}\log\langle W(C_{R,T})\rangle
=\sigma R+2\mu+\frac{2\mu R}{T}+\cdots.
$$

Taking $T\to\infty$ gives

$$
V_{\rm bare}(R)=\sigma R+2\mu+\cdots.
$$

The constant $2\mu$ is the static self-energy of the external charge and anticharge. After subtracting it,

$$
V(R)=\sigma R+\cdots.
$$

Thus an area law for a rectangular Wilson loop means that separating external probes costs energy proportional to their separation. The coefficient $\sigma$ is the string tension.

Physically, the flux does not spread out like an ordinary Coulomb field. It is compressed into a tube. Stretching the charges stretches the tube, and the tube has energy per unit length.

## Perimeter law means boundary-dominated behavior

A perimeter law for a rectangular loop gives

$$
\langle W(C_{R,T})\rangle
\sim \exp[-\mu 2(R+T)+\cdots].
$$

Then

$$
-\frac{1}{T}\log\langle W(C_{R,T})\rangle
=2\mu+\frac{2\mu R}{T}+\cdots.
$$

After subtracting the static-source self-energy, there is no term growing like $R$.

This does not always mean “nothing happens.” Perimeter behavior can arise for several different physical reasons:

| Mechanism | Interpretation |
|---|---|
| Screening by dynamical matter | The external probe charge is neutralized by particles from the vacuum. |
| Higgs phase | Electric charges are screened by a charged condensate. |
| Massive vector exchange | Forces are short-ranged; large loops pay mainly boundary cost. |
| Broken or absent one-form symmetry | The line charge is not conserved as a sharp asymptotic quantum number. |

Perimeter law is therefore less diagnostic by itself than area law. It says no stable sheet with tension $\sigma$ is forced across the loop, but it does not uniquely identify the phase.

## Coulomb behavior is neither area nor pure perimeter

A massless gauge field produces long-range interactions. For a rectangular Wilson loop in four-dimensional free electromagnetism, after subtracting perimeter self-energies, the dominant long-distance interaction is Coulombic:

$$
V(R)\sim -\frac{q^2}{4\pi R}.
$$

Thus

$$
\log\langle W(C_{R,T})\rangle
\sim +\frac{q^2}{4\pi}\frac{T}{R}
$$

for $T\gg R$, up to sign conventions for attractive or repulsive external charges and Euclidean normalization. The key scaling is $T/R$, not $RT$.

For a family of smooth loops of fixed shape scaled by $L$, a conformal or Coulombic theory can produce shape-dependent finite terms after perimeter renormalization. Calling this “perimeter law” without qualification hides the massless long-range physics. Better language is:

$$
\text{Coulomb phase}:\quad
\text{perimeter divergences plus scale-invariant long-range terms}.
$$

Area law, perimeter law, and Coulomb behavior are three different asymptotic patterns.

## Strong-coupling lattice origin of an area law

The lattice strong-coupling expansion makes the area law almost visual.

Put a gauge variable $U_\ell$ on each link of a Euclidean lattice. The Wilson action weights plaquettes. A Wilson loop inserts a trace of link variables around a closed curve $C$:

$$
W(C)=\frac{1}{N}\operatorname{tr}\prod_{\ell\in C}U_\ell.
$$

At strong coupling, expand the Boltzmann factor in powers of the plaquette coupling. Link integrals vanish unless every link variable is paired with enough conjugate variables to make a gauge-invariant group integral.

The Wilson loop supplies unpaired link variables along its boundary. The leading nonzero contribution comes from tiling a surface whose boundary is $C$ with plaquettes. If the minimal tiling contains $A_{\min}(C)/a^2$ plaquettes, then

$$
\langle W(C)\rangle
\propto u(\beta)^{A_{\min}(C)/a^2}
=\exp[-\sigma(\beta)A_{\min}(C)],
$$

where $u(\beta)$ is small at strong coupling and

$$
\sigma(\beta)a^2=-\log u(\beta)>0.
$$

This argument is beautifully direct. It also has a limit. Four-dimensional continuum Yang–Mills theory is reached by taking $a\to0$ along the asymptotically free continuum limit, where the bare lattice coupling is weak rather than strong. Showing that the area-law phase persists to that limit is a nonperturbative question. Lattice simulations strongly support it for pure Yang–Mills theory; a complete analytic proof remains out of reach.

## String breaking and intermediate area laws

In pure Yang–Mills theory, an external fundamental probe cannot be screened by gluons because gluons have zero center charge. In a theory with dynamical fundamental matter, the story changes.

Imagine an external quark–antiquark pair separated by $R$. At intermediate distances, the energy may look like

$$
V(R)\simeq \sigma R.
$$

But when $\sigma R$ exceeds twice the energy needed to create a heavy dynamical matter particle, the vacuum can produce a pair and break the string:

$$
V(R)\simeq \min(\sigma R,2M_{\rm static\text{-}light}).
$$

The Wilson loop then crosses over from an apparent area law to asymptotic perimeter behavior.

This is a common source of confusion. A Wilson loop can show an excellent area-law regime over accessible distances and still fail to have an asymptotic area law. Conversely, in lattice calculations, simple Wilson loops may have poor overlap with the broken-string state, so string breaking can be hard to see without including operators that explicitly represent two separated screened sources.

## Wilson and ’t Hooft loop comparison

The most useful phase table compares electric and magnetic line operators:

| Phase | Wilson loop | ’t Hooft loop | Static-probe interpretation |
|---|---|---|---|
| Confining pure gauge theory | Area law for unscreened center-charged probes | Perimeter law for dual magnetic probes | Electric flux tubes form. |
| Higgs phase | Perimeter law for screened electric probes | Area law for magnetic probes | Magnetic flux tubes form. |
| Coulomb phase | Coulomb behavior | Coulomb behavior | Massless gauge field mediates long-range forces. |
| Full QCD-like theory with fundamental matter | Intermediate area law possible; asymptotic string breaking | Depends on magnetic sector | Fundamental electric probes can be screened. |
| Oblique confinement | Area law for selected dyonic lines | Complementary dyonic lines screened | Condensed objects carry mixed electric-magnetic charge. |

The table is deliberately schematic. It is meant to train the eye: ask which line charge is conserved, which line operators are genuine, and which probes can be screened.

## Center symmetry refinement

In pure $SU(N)$ Yang–Mills theory, Wilson loops with nonzero $N$-ality are charged under a $\mathbb Z_N$ one-form center symmetry. An area law for such Wilson loops is naturally associated with an unbroken electric one-form symmetry in the confining regime. At finite temperature, the Polyakov loop becomes the more direct order parameter for center symmetry.

With dynamical fundamental matter, this one-form symmetry is explicitly broken. A fundamental Wilson line can end on a dynamical particle. Once the line can end, its asymptotic area law is not protected as a sharp symmetry diagnostic.

This is why the sentence “confinement means Wilson-loop area law” should always carry a footnote in the reader’s head:

$$
\text{sharpest in pure gauge theory, refined by center one-form symmetry}.
$$

Tiny footnote, huge amount of physics. Classic gauge-theory goblin behavior.

## Euclidean versus Lorentzian interpretation

The Wilson loop expectation value is usually computed in Euclidean signature:

$$
\langle W(C)\rangle_E\sim e^{-S_{\rm eff}[C]}.
$$

For a rectangular loop, one interprets the Euclidean time direction as the propagation time of external static sources. The exponent $T V(R)$ is then an energy times a Euclidean time.

The area $RT$ is not literally a spatial area in Lorentzian spacetime. It is the Euclidean worldsheet area swept out by the flux tube during propagation. This is why an area law becomes a potential energy in the Hamiltonian interpretation.

At finite temperature, loops wrapping the Euclidean thermal circle are Polyakov loops, and spatial Wilson loops have their own diagnostics. Do not mix these without checking which direction is Euclidean time.

## Common pitfalls

**Pitfall 1: forgetting perimeter renormalization.** Bare line operators have self-energy divergences proportional to their length. The physical question is whether a renormalized area term remains.

**Pitfall 2: using square loops to define a static potential.** A square loop can diagnose large-loop scaling, but the static potential comes from a rectangle with $T\to\infty$ at fixed $R$.

**Pitfall 3: equating perimeter law with deconfinement.** Perimeter behavior can mean screening, Higgs behavior, a massive phase, explicit breaking of one-form symmetry, or simply boundary-dominated ultraviolet physics.

**Pitfall 4: ignoring Coulomb phases.** A massless photon gives neither an area law nor a featureless perimeter law. It gives long-range scale-dependent or shape-dependent terms after perimeter subtraction.

**Pitfall 5: treating area law in full QCD as asymptotic.** Dynamical fundamental quarks can break the string. Pure Yang–Mills and full QCD have different line-operator diagnostics.

**Pitfall 6: taking the minimal surface too literally.** The notation $A_{\min}(C)$ captures scaling. In a fluctuating quantum theory, the effective string worldsheet fluctuates and has corrections such as Lüscher terms in appropriate regimes.

## Relations to other pages

[Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/) defines the loop and explains the static-potential extraction.

[’t Hooft Loops](/gauge-theories-standard-model/wilson-loops-confinement/thooft-loops/) explains the magnetic line operators whose area or perimeter laws give complementary phase diagnostics.

[Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/) explains why $N$-ality and global form are not optional decoration.

[Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/) explains how a string tension scale can emerge from a dimensionless gauge coupling.

The next pages in this chapter use these loop laws to discuss center symmetry, confinement, and the Polyakov loop.

## Research status

The connection between rectangular Wilson-loop area laws and linearly rising static potentials is standard. The lattice strong-coupling area-law derivation is also standard.

The hard question is continuum confinement in four-dimensional non-Abelian gauge theory. Pure Yang–Mills confinement and the mass gap are strongly supported by lattice evidence and theoretical arguments, but a full proof remains open.

In theories with dynamical matter, loop laws are more subtle. String breaking can turn an intermediate area law into asymptotic perimeter behavior. In theories with nontrivial global form, adjoint matter, supersymmetry, or discrete theta angles, one must analyze the full lattice of Wilson, ’t Hooft, and dyonic line operators. Modern higher-form symmetry gives the cleanest language for these refinements.

## Exercises

### Exercise 1: Area law and the static potential

Assume

$$
\langle W(C_{R,T})\rangle\sim e^{-\sigma RT-2\mu T-2\mu R}
$$

for $T\gg R$. Compute the static potential after subtracting the two static-source self-energies.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
V_{\rm bare}(R)=-\lim_{T\to\infty}\frac{1}{T}\log\langle W(C_{R,T})\rangle.
$$

Using the assumed form,

$$
V_{\rm bare}(R)=\sigma R+2\mu.
$$

The term $2\mu$ is the self-energy of the two static worldlines. After subtracting it,

$$
V(R)=\sigma R.
$$

</details>

### Exercise 2: Perimeter law and saturation

Assume

$$
\langle W(C_{R,T})\rangle\sim e^{-2\mu(R+T)-T V_\infty}
$$

for large $R$ and $T\gg R$. What is the asymptotic static potential after subtracting the static-source self-energy?

<details><summary><strong>Solution</strong></summary>

The bare potential is

$$
V_{\rm bare}(R)=2\mu+V_\infty.
$$

Subtracting the two static-source self-energies gives

$$
V(R)=V_\infty.
$$

Thus the potential saturates rather than growing linearly. This is typical of screening or string breaking.

</details>

### Exercise 3: String-breaking scale

Suppose a theory has an intermediate confining potential $V(R)=\sigma R$ but can break the string into two screened static-light objects of total energy $2M$. Estimate the crossover distance.

<details><summary><strong>Solution</strong></summary>

String breaking becomes energetically favorable when

$$
\sigma R\simeq 2M.
$$

Thus the crossover distance is roughly

$$
R_{\rm break}\simeq \frac{2M}{\sigma}.
$$

For $R\ll R_{\rm break}$ the potential can look linear. For $R\gg R_{\rm break}$ the lower-energy state is the screened two-object state, so the potential saturates.

</details>

### Exercise 4: Scaling with loop size

Let $C_L$ be a family of similar loops scaled by $L$. Show that an area law grows like $L^2$ in the exponent while a perimeter law grows like $L$.

<details><summary><strong>Solution</strong></summary>

Under scaling by $L$, lengths scale as $L$ and areas scale as $L^2$:

$$
P(C_L)=L P(C_1),
\qquad
A_{\min}(C_L)=L^2A_{\min}(C_1).
$$

Therefore a perimeter law gives

$$
-\log\langle L(C_L)\rangle\sim \mu L P(C_1),
$$

while an area law gives

$$
-\log\langle L(C_L)\rangle\sim \sigma L^2 A_{\min}(C_1).
$$

The area-law exponent dominates parametrically at large $L$ when $\sigma\neq0$.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §82, for Wilson loops, strong-coupling lattice area laws, and confinement.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for Wilson lines, lattice gauge theory, Yang–Mills running, and QCD-oriented interpretation.
- Polyakov, *Gauge Fields and Strings*, Chs. 5 and 7, for phase-factor criteria, confinement analogies, and loop dynamics.

### Deeper references

- Wilson, “Confinement of Quarks,” for the original lattice Wilson-loop area-law criterion.
- Kogut, “An Introduction to Lattice Gauge Theory and Spin Systems,” for strong-coupling expansions and lattice gauge theory.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for center one-form symmetry and line-operator language.
- Greensite, *An Introduction to the Confinement Problem*, for an extended modern discussion of Wilson loops, string tensions, center symmetry, and confinement scenarios.

## Version history

- **2026-06-18:** Initial polished draft. Added area/perimeter definitions, static-potential extraction, Coulomb behavior, strong-coupling lattice origin, string breaking, center-symmetry refinement, and exercises.
